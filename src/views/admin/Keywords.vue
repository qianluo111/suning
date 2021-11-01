<template>
  <div class="wrap">
    <div class="zengjia">
      <a-button class="btn" type="primary" @click="showModal" style="margin:22px 0">
        增加舆情关键词
      </a-button>
    </div>
    <a-modal v-model="visible" title="增加舆情关键词" @ok="handleOk">
      <p>
        必须包含关键词:
        <input
          type="text"
          placeholder="必须包含关键词"
          style="margin-left: 15px;"
        />
      </p>
      <p>
        可包含关键词:
        <input
          type="text"
          placeholder="可包含关键词"
          style="margin-left: 27px;"
        />
      </p>
      <p>
        不包含关键词:
        <input
          type="text"
          placeholder="不包含关键词"
          style="margin-left: 25px;"
        />
      </p>
      <p>
        监控频率:
        <input type="text" placeholder="监控频率" style="margin-left: 52px;" />
      </p>
    </a-modal>
    <a-table :columns="columns" :data-source="data" style="margin-top:20px">
      <a slot="name" slot-scope="text">{{ text }}</a>
    </a-table>
     <template slot="action" slot-scope="text">
            <a-button type="primary" @click="doEdit(text.key)">编辑</a-button>
            <a-button type="danger">删除</a-button>
        </template>
  </div>
</template>
<script>
const columns = [
  {
    title: "必须包含关键词",
    dataIndex: "name",
    key: "keywords",
    scopedSlots: { customRender: "name" },
  },
  {
    title: "可包含关键词",
    dataIndex: "age",
    key: "age",
    width: 200,
  },
  {
    title: "不包含关键词",
    dataIndex: "address",
    key: "address 1",
    ellipsis: true,
  },
  {
    title: "监控频率",
    dataIndex: "address",
    key: "address 2",
    ellipsis: true,
  },
  {
    title: "操作",
    dataIndex: "address",
    key: "address 3",
    ellipsis: true,
  },
];
const listData = [
  {
    id: 1,
    keyword: "大庆油田",
    may_keyword: "中国石油",
    nokeyword: "延长石油",
    frequency: "100",
  },
  {
    id: 2,
    keyword: "贪污",
    may_keyword: "腐败",
    nokeyword: "打腐败",
    frequency: "100",
  },
];

const data = [
  {
    key: "1",
    name: "John Brown",
    age: 32,
    address: "New York No. 1 Lake Park, New York No. 1 Lake Park",
    tags: ["nice", "developer"],
  },
  {
    key: "2",
    name: "Jim Green",
    age: 42,
    address: "London No. 2 Lake Park, London No. 2 Lake Park",
    tags: ["loser"],
  },
  {
    key: "3",
    name: "Joe Black",
    age: 32,
    address: "Sidney No. 1 Lake Park, Sidney No. 1 Lake Park",
    tags: ["cool", "teacher"],
  },
];
export default {
  data() {
    return {
      data,
      listData,
      columns,
      visible: false,
    };
  },
  methods: {
    showModal() {
      this.visible = true;
    },
    handleOk(e) {
      console.log(e);
      this.visible = false;
    },
  },
};
</script>


<style scoped>
.wrap {
  background: #fff;
  width: 100%;
  height: 700px;
}
.btn{
  height: 30px;
  line-height:30px;
  display:flex;
}
input {
  width: 395px;
  height: 30px;
  outline: none;
  border: 1px solid rgb(217, 217, 217);
  color: rgba(167, 162, 162, 0.274);
  padding-left: 5px;
  font-size: 10px;
}


p {
  color: black;
  font-weight: bold;
}
.zengjia {
  width: 100%;
  display: flex;
  background: #fffced;
  height: 80px;
}
</style>
