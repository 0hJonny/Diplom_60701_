```Mermaid MD UML
graph LR;
    subgraph Project["IT News"]

        SaveToDB(Сохранить статью в хранилище);
        LoadFromDB(Прочитать статью из хранилища);
        DoSumary(Создать summary по статьям);
        DoFindCategory(Определить категорию статьи);

        DoCheckSite(Периодически прочитать страницу со списком статей);
        DoCheckArticleFromDB(Проверить наличие статей в хранилище);
        DoReadArticel(Прочитать статью);

        UserExp(Использует сайт)
        CheckArticles(Просмотр последних статей);
        CheckCategory(Поиск по категориям);
        ContextSearch(Контекстный поиск);

        CheckArticles --> UserExp;
        CheckCategory --> UserExp;
        ContextSearch --> UserExp;


        DoSumary -.->|extend| DoReadArticel;
        DoFindCategory -.->|extend| DoReadArticel;
        
    end

    
Service[Сервис];
    Service --- SaveToDB;
    Service --- LoadFromDB;
    Service --- DoCheckArticleFromDB;
    Service --- DoCheckSite;
    Service --- DoReadArticel;

Reader[Читатель];
    Reader --- UserExp;

ChatGPT["AI ChatGPT"];
ChatGPT --- DoSumary;
ChatGPT --- DoFindCategory;
```
