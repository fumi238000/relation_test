# README

## 概要
１対多の関係性において、rails cで情報を取得する方法をテストするために作成


## テーブル
```
  create_table "posts", force: :cascade do |t|
    - t.string "content", null: false
    - t.bigint "user_id", null: false
    - t.datetime "created_at", precision: 6, null: false
    - t.datetime "updated_at", precision: 6, null: false
    - t.index ["user_id"], name: "index_posts_on_user_id"
  end
  
   create_table "users", force: :cascade do |t|
    - t.string "email", default: "", null: false
    - t.string "encrypted_password", default: "", null: false
    - t.string "reset_password_token"
    - t.datetime "reset_password_sent_at"
    - t.datetime "remember_created_at"
    - t.datetime "created_at", precision: 6, null: false
    - t.datetime "updated_at", precision: 6, null: false
    - t.index ["email"], name: "index_users_on_email", unique: true
    - t.index ["reset_password_token"], name: "index_users_on_reset_password_token", unique: true
  end

  add_foreign_key "posts", "users"
end
```

