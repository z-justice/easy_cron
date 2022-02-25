<template>
  <div class="main-content">
    <div class="card-content">
      <div class="form-list">
        <Form :model="formData" :rules="formDataValidator" :label-width="80">
          <FormItem label="cron表达式" prop="cronValue">
            <input-cron
              type="text"
              v-model="formData.cronValue"
              :exeStartTime="exeStartTime"
              :hideSecond="true"
              placeholder="请输入cron表达式"
            />
          </FormItem>
        </Form>
      </div>
    </div>
  </div>
</template>

<script>
import EasyCron from "./easy-cron";
import InputCron from "./easy-cron/input-cron";
import CronValidator from "./easy-cron/validator";

export default {
  name: "HelloWorld",
  data() {
    return {
      exeStartTime: "2015-09-02 12:23:10",
      formData: {
        cronValue: ""
      },
      formDataValidator: {
        cronValue: [{ validator: CronValidator }]
      }
    };
  },
  methods: {},
  components: {
    EasyCron,
    InputCron
  },
  created() {
    // console.info(aaa)
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
.main-content {
  /* // background-color: #E0E0E0; */
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
  height: 100%;
}

.card-content {
  flex-basis: 600px;
}

.form-list {
  margin-top: 20px;
}
</style>
