classDiagram
direction BT
class annotations {
   integer article_id
   text annotation
   bigint id
}
class articles {
   varchar(255) title
   date publication_date
   varchar(255) author
   integer theme_id
   varchar(255) source_link
   varchar(255) image_link
   text body
   bigint id
}
class themes {
   varchar(255) theme_name
   integer theme_id
}

annotations  -->  articles : article_id:id
articles  -->  themes : theme_id
