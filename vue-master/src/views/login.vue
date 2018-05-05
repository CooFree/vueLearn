

<template>
    <div class="login">
        <div class="loginDiv">
            <div class="title text-center"  @click='show'>壹基因社区</div>
            <div class="commondiv">
                <p style="margin-bottom:0.1rem;">手机号</p>
                <p><input placeholder="请输入手机号" v-model="accouont"></p>
            </div>
            <div class="commondiv">
                <p style="margin-bottom:0.1rem;">密码</p>
                <p><input type="password" placeholder="请输入密码" v-model="password"></p>
            </div>
            <div class="commondiv clrarfix">
                <span class="fl"><span style="color: #999999;">还没有账号</span> <a class="blue" @click='go("register")'>注册</a></span>
                <a class="fr blue" @click='go("loginByCode")'>验证码登录</a>
            </div>
            <div class="bottomBtn">
                <button @click="commit">登录</button>
            </div>
        </div>
        <div class="popdiv" v-show="visible" ref="main" @click='show'>
            <div class="popContent">
            <div class="popContentDetail">蜂投理财新系统上线以后 ，针对新的调整做以下调整：</div>
            <div class="popContentTitle">1、投资</div>
            <div class="popContentDetail">新系统上线以后 ，新手福利 、机构标、蜂计划产品标的会迁移到新的投资通道（存管），新老用户需要投资新手福利、机构标、蜂计划产品时需要进行实名认证并开通上饶银行存管账户</div>
            <div class="popContentTitle">2、原汇付账户处理</div>
            <div class="popContentDetail">新系统上线以后 ，在完成数据迁移之前 ，原汇付数据将会进行保留（包括标的数据（前台不展示）、投资数据、账户数据、资金数据）。</div>
            <div class="popContentDetail">老用户在汇付充值的资金、投资账单、回款都会得到保留以及查询，同时依然保留充值与提现功能，方便用户进行提现操作。</div>
            <div class="popContentDetail">新用户不需要进行汇付账户的开设，只要进行实名认证并开通银行存管账户就可以进行投资。</div>
            <div class="popContentTitle">3、债权转让</div>
            <div class="popContentDetail">新系统上线以后 ，新的存管暂不支持债权转让，但仍然保留汇付的债权转让，要投资债权转让标的 ，需是老用户且开通了汇付账户才能进行投资，新用户暂不支持债权转让。</div>
            <div class="popContentTitle">4、充值</div>
            <div class="popContentDetail">开通存管账户后，账户在将存在两个账户，一个是网贷账户，一个理财账户，两个账户的资金不能互通，充值的时候请根据要进行投资的产品选择相应账户进行充值，避免充值以后不能投资。</div>
            </div>
        </div>
    </div>
</template>

<script>
import { MessageBox } from "mint-ui";

export default {
  name: "Login",
  data() {
    return {
      visible: true,
      accouont: "",
      password: "",
      path: ""
    };
  },
  mounted: function() {},
  methods: {
    show() {
      this.visible = !this.visible;
    },
    commit() {
      if (!this.accouont) {
        MessageBox.alert("请输入手机号码").then(action => {});
        return false;
      }
      if (!this.password) {
        MessageBox.alert("请输入密码");
        return false;
      }
      this.$router.push("index");
    },
    go(name) {
      this.$router.push(name);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.popContent {
    width: 50%;
    height: 30%;
    background-color: #fff;
    margin-left: 25%;
}
.popContentTitle {
    color: rgba(124, 120, 120, 0.664);
    font-size: 10px;
    margin: 5px 0 5px 0;
}
.popContentDetail {
    color: rgba(39, 34, 34, 0.521);
    font-size: 15px;
    margin: 5px 0 5px 0;
}
.popdiv {
  width: 100%;
  height: 100%;
  position: fixed;
  bottom: 0px;
  background-color: #dfdfdfce;
}
.login {
  width: 100%;
  width: 100%;
  padding-top: 0.88rem;
}
.loginDiv {
  padding: 0 0.3rem;
  font-size: 0.32rem;
  color: #3a3a3a;
}
.title {
  padding: 0.81rem 0 1.35rem 0;
  font-size: 0.36rem;
}
.commondiv {
  margin-bottom: 0.3rem;
}
.commondiv input {
  width: 100%;
  border: none;
  border-bottom: 1px solid #ccc;
  height: 0.5rem;
  line-height: 0.5rem;
  border-radius: 0;
  background: #f7f7f7;
}
.commondiv input:focus {
  border-bottom: 1px solid #448aff;
}
.bottomBtn {
  margin-top: 1.5rem;
}
.bottomBtn button {
  width: 100%;
  height: 0.74rem;
  color: #fff;
  background: #448aff;
  border: 1px solid #448aff;
  font-size: 0.36rem;
  border-radius: 4px;
}
</style>