<template>
  <view class="index">
    <Form @submit="onSubmit">
      <Tabs v-model:active="active">
        <Tab title="商业贷">
          <CellGroup>
            <Field v-model="total" type="number" name="total" label="贷款总额" placeholder="贷款总额（万）" input-align="right"
                   :rules="[{ required: true, message: '' }]"/>
          </CellGroup>
        </Tab>
        <Tab title="公积贷款">
          <CellGroup>
            <Field v-model="total" type="number" name="total" label="贷款总额" maxplaceholder="贷款总额（万）" input-align="right"
                   :rules="[{ required: true, message: '' }]"/>
          </CellGroup>
        </Tab>
      </Tabs>

      <div style="margin: 16px;">
        <Button round block type="primary" size="large" native-type="submit" @onClick="onSubmit">
          开始计算
        </Button>
      </div>
    </Form>
  </view>
</template>

<script>
  import Taro from '@tarojs/taro'
  import {
    Button,
    Tabs,
    Tab,
    Icon,
    Form,
    Field,
    Stepper,
    CellGroup,
    NoticeBar,
    Swipe,
    SwipeItem,
    List,
    Cell
  } from 'vant';

  export default {
    name: 'Index',
    components: {
      Button,
      Tabs,
      Tab,
      Icon,
      Form,
      Field,
      Stepper,
      CellGroup,
      NoticeBar,
      Swipe,
      SwipeItem,
      List,
      Cell,
    },
    data() {
      return {
        active: 0,
        total: '',
        years: 30,
        months: 12,
        rate: 5.25,
        onceRate: 0,
        repaymentMonth: 0,
        rateUnit: '%',
        rateUnitIconName: 'money',
        onceRateUnit: '%',
        onceRateUnitIconName: 'money',
        loading: false,
        finished: false,
        bills: []
      };
    },
    methods: {
      onSubmit(values) {
        console.log(values)
      },
      onLoad() {
      },
      mounted() {
        console.log("ddd333")
      },
    }
  }
</script>

<style>
  html {
    background-color: #f5f5f5;
  }

  .index {
    font-family: "Avenir", Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin: 60px 40px 10px;
    background-color: #fff;
    border-radius: 16px;
    padding: 20px;
  }

  .compute-tips {
    font-size: 14px;
    color: #999;
    margin: 5px;
    text-align: center;
  }

  .tips {
    margin: 20px 0;
  }

  .notice-swipe {
    height: 40px;
    line-height: 40px;
  }

  .van-field__button {
    width: 24px;
  }
</style>
