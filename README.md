# テーブル設計

## users テーブル

| Column                 | Type       | Options      |
|------------------------|------------|--------------|
| name                   | string     | null: false  |  
| nickname               | string     | null: false  | 
| email                  | string     | null: false  | 
| encrypted_password     | string     | null: false  | 


- has_many :steps
- has_many :messages


# steps テーブル

| Column                 | Type       | Options                         |
|------------------------|------------|---------------------------------|
| steps                  | string     |                                 |  
| user                   | references | null: false, foreign_key: true  | 

- belongs_to :user
- has_many :messages


# messagesテーブル

| Column                 | Type       | Options                         |
|------------------------|------------|---------------------------------|
| text                   | text       |                                 |  
| user                   | references | null: false, foreign_key: true  | 
# image はActiveStrongで実装

- belongs_to :user
- has_many :steps

