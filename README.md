可以通过API创建Notion文档。以下是一个使用Python编写的完整代码示例，展示如何通过Notion API创建一个新的页面。

### 前提条件
1. **创建Notion集成**：首先，你需要在Notion中创建一个集成，并获取API令牌。可以参考[官方文档](https://developers.notion.com/docs/create-a-notion-integration)。
2. **安装依赖**：需要安装`notion-client`库，可以通过以下命令安装：
   ```bash
   pip install notion-client
   ```

### 完整代码示例
以下是一个Python脚本，展示如何使用Notion API创建一个新的页面：

```python
import os
from notion_client import Client

# 设置Notion API令牌
NOTION_TOKEN = ""
DATABASE_ID = ""

# 初始化Notion客户端
notion = Client(auth=NOTION_TOKEN)

  # 创建一个新的页面
new_page = notion.pages.create(
      parent={"database_id": DATABASE_ID},
      properties={
          "title": {
              "title": [
                  {
                      "type": "text",
                      "text": {
                          "content": f"123"
                      }
                  }
              ]
          }
      },
      children=[
          {
              "object": "block",
              "type": "paragraph",
              "paragraph": {
                  "rich_text": [
                      {
                          "type": "text",
                          "text": {
                              "content": f"123"
                          }
                      }
                  ]
              }
          }
      ]
  )

mm = new_page['id'].replace("-","")
titleb = "123".replace(" ","-")
print(f"https://www.notion.so/{titleb}{mm}?pvs=4")
```

### 代码说明
1. **导入库**：导入`os`和`notion_client`库。
2. **设置API令牌和数据库ID**：将你的Notion集成令牌和数据库ID设置为变量。
3. **初始化Notion客户端**：使用令牌初始化Notion客户端。
4. **创建页面的数据**：定义新页面的数据，包括父数据库ID和页面属性（如名称、描述和日期）。
5. **创建新页面**：调用`notion.pages.create`方法创建新页面，并传入页面数据。
6. **打印响应**：打印API响应，确认页面创建成功。

### 注意事项
- 确保你已经在Notion中创建了一个数据库，并将其ID替换到代码中的`DATABASE_ID`变量中。
- 确保你的Notion集成具有对目标数据库的写入权限。

通过以上步骤，你可以使用Python脚本通过Notion API创建新的页面。如果有任何问题，请参考[Notion API文档](https://developers.notion.com/reference/post-page)。

Citations:
[1] https://developers.notion.com/reference/post-page
[2] https://www.notion.so/templates/api-docs
[3] https://github.com/ramnes/notion-sdk-py
[4] https://www.youtube.com/watch?v=M1gu9MDucMA
[5] https://developers.notion.com/docs/create-a-notion-integration
[6] https://notion-lab.jp/2023-09-30-python-notion-api/
[7] https://www.python-engineer.com/posts/notion-api-python/
[8] https://www.notion.so/help/guides/connect-tools-to-notion-api
[9] https://qiita.com/Yusuke_Pipipi/items/b44cb8442932019c52c9
[10] https://airbyte.com/pyairbyte/notion-python
[11] https://engine.so/blog/how-to-use-notion-for-api-documentation-w-free-template/
[12] https://thienqc.notion.site/Notion-API-Python-ca0fd21bc224492b8daaf37eb06289e8
[13] https://www.notion.so/help/code-blocks
[14] https://www.notion.so/help/create-integrations-with-the-notion-api
[15] https://zenn.dev/team_zenn/articles/117424abb5605b
[16] https://www.youtube.com/watch?v=KENSTonsiEc
[17] https://www.notion.so/templates/no-code-api-documentation-publish
[18] https://qiita.com/kuro221/items/b25361db5007ce944c04
[19] https://www.pynotion.com/create-databases/
[20] https://apitoolkit.io/blog/using-notion-for-documentation/
