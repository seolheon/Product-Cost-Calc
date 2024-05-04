<template>
  <el-container>
    <el-header class="calc-header">
      <div class="h-wrapper">
        <h1>Product Cost Calc</h1>
      </div>

      <el-button type="primary" :icon="ShoppingCart" />
    </el-header>

    <el-main class="card">

      <section class="dropdown-section">
        <div class="dropdown-wrapper">
          <label class="c-label">Choose category</label>
          <el-dropdown @command="handleCommand">
            <span class="dropdown-link">
              Dropdown List<el-icon class="el-icon--right"><arrow-down /></el-icon>
            </span>
            <template #dropdown>
              <el-dropdown-menu class="dropdown-menu">
                <el-dropdown-item command="a">Action 1</el-dropdown-item>
                <el-dropdown-item command="b">Action 2</el-dropdown-item>
                <el-dropdown-item command="c">Action 3</el-dropdown-item>
                <el-dropdown-item command="d" disabled>Action 4</el-dropdown-item>
                <el-dropdown-item command="e" divided>Action 5</el-dropdown-item>
              </el-dropdown-menu>
            </template>
          </el-dropdown>
        </div>   

        <div v-show="true" class="dropdown-wrapper">
          <label class="c-label">Choose product</label>
          <el-dropdown @command="handleCommand">
            <span class="dropdown-link">
              Dropdown List<el-icon class="el-icon--right"><arrow-down /></el-icon>
            </span>
            <template #dropdown>
              <el-dropdown-menu class="dropdown-menu">
                <el-dropdown-item command="a">Action 1</el-dropdown-item>
                <el-dropdown-item command="b">Action 2</el-dropdown-item>
                <el-dropdown-item command="c">Action 3</el-dropdown-item>
                <el-dropdown-item command="d" disabled>Action 4</el-dropdown-item>
                <el-dropdown-item command="e" divided>Action 5</el-dropdown-item>
              </el-dropdown-menu>
            </template>
          </el-dropdown>
        </div>  
      </section>
    
      <section class="product-details">
        <div class="image-wrapper">
          <img class="product-image" src="../assets/birch.jpg"/>
        </div>
        <div class="description-wrapper">
          <label class="name">Name</label>
          <label class="cost">Cost</label>
          <div class="qauntity-selection"> 
            <label>Quantity</label>
            <input id="quantity-input"/>
          </div>
          <el-button type="primary">Add to cart</el-button>
        </div>
      </section>

    </el-main>
    <el-footer></el-footer>
  </el-container>
</template>

<script lang="ts" setup>
import { ElMessage } from 'element-plus'
import { ArrowDown, ShoppingCart } from '@element-plus/icons-vue'

const handleCommand = (command: string | number | object) => {
  ElMessage(`click on item ${command}`)
}
</script>

<style scoped>

.calc-header {
  background-color: #303030;
  width: 100vh;
  display: flex;
  justify-content: space-between;
  place-items: center;
  border-radius: 10px 10px 0px 0px;
}

.h-wrapper {
  color: #909090;
  font: 18px Montserrat Alternates, -apple-system, Roboto, Helvetica, sans-serif;
}

.card {
  background-color: #303030;
  border-radius: 0px 0px 10px 10px;
}

.dropdown-section {
  display: flex;
  justify-content: center;
  place-items: center;
  gap: 100px;
}

.dropdown-wrapper {
  background-color: #202020;
  border-radius: 10px;
  display: flex;
  justify-content: center;
  place-items: center;
  gap: 20px;
  padding: 10px 10px;
}

.c-label {
  color: #909090;
  font: 400 14px Montserrat Alternates, -apple-system, Roboto, Helvetica, sans-serif;
}

.product-details {
  display: flex;
  justify-content: center;
  place-items: center;
  gap: 50px;
  margin: 30px 0px 50px 0px;
}

.description-wrapper {
  display: flex;
  flex-direction: column;
  gap: 10px;
  color: #909090;
  font: 400 14px Montserrat Alternates, -apple-system, Roboto, Helvetica, sans-serif;
}

.qauntity-selection {
  margin-bottom: 15px;
  display: flex;
  flex-direction: row;
  place-items: center;
  gap: 15px;
}

#quantity-input {
  background-color: #202020;
  border-radius: 10px;
  color: #909090;
  padding-left: 10px;
  border: none;
}

.product-image {
  max-width: 130px;
}


.dropdown-link {
  cursor: pointer;
  color: #909090;
  background-color: #202020;
  display: flex;
  align-items: center;
  font: 400 14px Montserrat Alternates, -apple-system, Roboto, Helvetica, sans-serif;
}

.dropdown-menu{
  cursor: pointer;
  background-color: #202020;
  display: flex;
  flex-direction: column;
  font: 400 14px Montserrat Alternates, -apple-system, Roboto, Helvetica, sans-serif;
}
</style>