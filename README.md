
## baseUrl = 'http://10.36.136.170:9999'


## TodoList功能的接口文档

* 获取我的所有任务（包括待完成和未完成的任务）

```
  GET  /todo/getMyTodos
  入参：
  {
    userId: String,    // 你的学号，必填
  }
  出参示例：
  {
    "err": 0,
    "msg": "success",
    "data": {
      // 待完成的任务列表
      "undone": [    
        {
            "_id": "5e0189667e18221ee819c777",   // 任务id
            "userId": "1",                       // 你的学号
            "task": "跑步",                      // 任务名称
            "status": "0",                       // 任务的状态，0-待完成  1-已完成
            "createTime": 1577159014331,         // 任务的创建时间
            "__v": 0
        }
      ],
      // 已完成的任务列表
      "done": [    
          {
              "_id": "5e0189627e18221ee819c776",
              "userId": "1",
              "task": "跑步2233",
              "status": "1",
              "createTime": 1577159010121,
              "__v": 0
          }
      ]
    }
  }
```

* 添加一条新任务
```
  POST  /todo/addTodo
  入参：
  {
    userId: String,   // 你的学号，必填
    task: String      // 任务名称，必填
  }
```

* 删除一条任务
```
  GET  /todo/deleteTodo
  入参：
  {
    userId: String,    // 你的学号，必填
    id: String,        // 任务的id
  }
```

* 切换任务的状态
```
  GET  /todo/changeTodoStatus
  入参：
  {
    userId: String,   // 你的学号，必填
    id: String,       // 任务id
    status: String,   // '0'-表示把任务变成“正在进行”  '1'-表示把任务变成“已完成”
  }
```

* 修改任务名称
```
  POST  /todo/editTodo
  入参：
  {
    userId: String,   // 你的学号
    id: String,       // 当前任务id
    task: String      // 新的任务名称
  }
```
