<template>
  <div>
    <navbar />
    <el-container style="height: 500px; border: 1px solid #eee">
      <el-aside width="100px">
        <el-row type="flex" class="row-bg" justify="center">
          <el-button type="success" icon="el-icon-plus" circle></el-button>
        </el-row>
        <el-row type="flex" class="row-bg" justify="center">
          <el-button type="text" icon="el-icon-menu" circle></el-button>
        </el-row>
        <el-row type="flex" class="row-bg" justify="center">
          <el-button type="text" icon="el-icon-s-operation" circle></el-button>
        </el-row>
        <el-row type="flex" class="row-bg" justify="center">
          <el-button type="text" icon="el-icon-s-data" circle></el-button>
        </el-row>
      </el-aside>

      <el-container>
        <el-main>
          <el-row>
            <el-button size="small" type="success" round>Finish sprint</el-button>
          </el-row>
          <h3>
            Sprint overview
            <el-button size="small" round>Last sprint</el-button>
          </h3>
          <el-row :gutter="5">
            <el-col :span="6">
              <el-card class="box-card">
                <i class="el-icon-s-marketing"></i>
                <p>Team velocity</p>
                <h4>52</h4>
              </el-card>
            </el-col>
            <el-col :span="6">
              <el-card class="box-card">
                <i class="el-icon-user"></i>
                <p>Team members</p>
                <h4>12</h4>
              </el-card>
            </el-col>
            <el-col :span="6">
              <el-card class="box-card">
                <i class="el-icon-takeaway-box"></i>
                <p>Tasks delivered</p>
                <h4>23</h4>
              </el-card>
            </el-col>
            <el-col :span="6">
              <el-card class="box-card">
                <i class="el-icon-search"></i>
                <p>Spikes delivered</p>
                <h4>15</h4>
              </el-card>
            </el-col>
          </el-row>
          <el-row :gutter="5">
            <el-col :span="12">
              <h3>Burndown chart</h3>
            </el-col>
            <el-col :span="12">
              <h3>
                Sprint stories
                <el-button size="small" round>See all</el-button>
              </h3>
              <el-table
                :data="tableData"
                style="width: 100%">
                <el-table-column
                  prop="id"
                  label="ID"
                  width="180">
                </el-table-column>
                <el-table-column
                  prop="name"
                  label="Name"
                  width="180">
                </el-table-column>
                <el-table-column
                  prop="status"
                  label="Status">
                </el-table-column>
                <el-table-column
                  prop="hours"
                  label="Hours">
                </el-table-column>
              </el-table>
            </el-col>
          </el-row>
        </el-main>
      </el-container>
      <el-aside width="200px"></el-aside>
    </el-container>
  </div>
</template>

<script>
  import Navbar from '~/components/Navbar.vue';

  export default {
    data() {
      const item = {
        id: 'P42',
        name: 'UI design',
        status: 'Delivered',
        hours: 12
      };
      return {
        tableData: Array(3).fill(item)
      }
    },
    components: {
      Navbar
    }
  };
</script>

<style>
  .row-bg {
    margin-top: 2em;
  }

  .el-header {
    background-color: #B3C0D1;
    color: #333;
    line-height: 60px;
  }

  .el-aside {
    color: #333;
  }
</style>
