# i18n対応

Potファイルを作成後、それをもとに該当言語のPoファイルを作成し、翻訳の編集を行います。
i18n対応が必要なファイルはmako, js, html(admin画面)などがあります。

＜potファイルの作成コマンド＞
mako：pybabel extract -F ./website/settings/babel.cfg -o ./website/translations/messages.pot .
js：pybabel extract -F ./website/settings/babel_js.cfg -o ./website/translations/js_messages.pot .
html；django-admin makemessages --keep-pot -l ja

＜poファイルの作成、更新＞
mako；pybabel update -i ./website/translations/messages.pot -d ./website/translations -l ja --update-header-comment --previous
js；ybabel update -i ./website/translations/js_messages.pot -D js_messages -d ./website/translations -l ja --update-header-comment --previous
html；pybabel update -i ./admin/translations/django.pot -D django -d ./admin/translations -l ja --update-header-comment --previous(事前にdajngo.potファイルのProject-Id-Version等の属性の記法をpybabelに合わせておく)
