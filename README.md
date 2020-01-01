# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

# MaiduruSightseeing DB設計

## shop_personsテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false, unique: true|
|phone_number|string|null: false, unique: true|
|password|string|null: false|
|shop_name|string|null: false|
|person_name|string|null: false|
### Association
- has_many :information
- belongs_to :category

## informationsテーブル
|Column|Type|Options|
|------|----|-------|
|image|text|null: false|
|text|text|null: false|
|shop_person_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :shop_person

## categoriesテーブル
|Column|Type|Options|
|------|----|-------|
|genre|string|null: false,unique: true|
|ancestry|string||
### Association
- has_many :shop_person
- has_ancestry