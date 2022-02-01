<template>
  <div>
   <el-button  type="primary"  icon="el-icon-plus"  @click="showAddDialog"
   >添加</el-button
   >

   <el-table :data="trademarkList" border  style="width: 100%;margin:2px 0">

     <el-table-column type="index" align="center" label="序号" width="80">
     </el-table-column>

     <el-table-column prop="tmName" label="品牌名称" width="width">
     </el-table-column>

     <el-table-column label="品牌LOGO" width="width">
       <template  slot-scope="{ row, $index }">
         <img :src="row.logoUrl" alt=" "   style="width:80px;height:60px" />
       </template>
     </el-table-column>

     <el-table-column prop="prop" label="操作" width="width">
       <template slot-scope="{ row, $index }">
         <el-button 
         type="warning"  
         icon="el-icon-edit" 
         size="mini"   
         @click="showUpdateDialog(row)"
         >修改</el-button
         >
         <el-button  
         type="danger"  
         icon="el-icon-delete"  
         size="mini"  
         @click="deleteTrademark(row)"
         >删除</el-button
         >
       </template>
     </el-table-column>
   </el-table>

   <el-pagination 
   style="text-align: center" 
   layout="prev, pager, next, jumper,->,sizes,total"
   @current-change="getTrademarkList"  
   @size-change="handleSizeChange" 
   :page-sizes="[3, 5, 10]" 
   :page-count="5"  
   :current-page="page"  
   :page-size="limit"
   :total="total"
   >
   </el-pagination>
   
   <el-dialog 
   :title="tmForm.id ? '修改品牌' : '添加品牌'"
   :visible.sync="dialogFormVisible"
   >
  <el-form  style="width:80%" :model="tmForm" :rules="rules"  ref="tmForm">
    <el-form-item label="品牌名称" label-width="100px" prop="tmName">
      <el-input v-model="tmForm.tmName"  autocomplete="off"></el-input>
    </el-form-item>

    <el-form-item label="品牌Logo" label-width="100px"  prop="logoUrl">
      <el-upload
      class="avatar-uploader"
      action="dev-api-/admin/product/fileUpload"
      :show-file-list="false"
      :on-success="handleAvatarSuccess"
      :before-upload="beforeAvatarUpload"
      >
      <img v-if="tmForm.logoUrl" :src="tmForm.logoUrl" class="avatar" />
      <i v-else class="el-icon-plus avatar-uploader-icon"></i>
      <div class="el-upload__tip"  slot="tip">
        只能上传jpg/png文件，且不超过500kb
        </div>
      </el-upload>
    </el-form-item>
  </el-form>

  <div slot="footer" class="dialog-footer">
    <el-button  @click="dialogFormVisible  =  false">取消</el-button>
    <el-button  type="primary"  @click="addOrUpdateTrademark"
    >确定</el-button
    >
  </div>
   </el-dialog>
  </div>
</template>

<script>
export default {
    name: "Trademark",
    data()   {
      var  validateTmName   =   (rule, value, callback)   =>  {
        
      }
    }
}
</script>

<style>

</style>