# コーディング規約

## 目次

1\. 言語共通<br>
2\. Java<br>
3\. Python<br>
4\. HTML（HTML テンプレートを含む）<br>
5\. SQL<br>

## 1. 言語共通

* ファイルエンコーディングは、UTF-8 とする。
* 改行コードは、UNIX 改行（CR）とする。（プロジェクト判断とする）
* ハンガリー記法（bFlag、iValue 等）は、使用しない。
* アッパーキャメルケース、キャメルケース、スネークケースについて：
    ```
    WriteFile ← アッパーキャメルケース
    writeFile ← キャメルケース
    write_file ← スネークケース
    ```
* 関数名やメソッド名は、基本的に “[助動詞 ＋] 動詞 + 名詞” とする。
    |<center>キャメルケース</center>|<center>スネークケース</center>|<center>復帰値例<center>|<center>補足<center>|
    |:--|:--|:--|:--|
    |isValid|is_valid|Boolean|有効性判定|
    |hasXxxx|has_xxxx|Boolean|xxxxを持っているか否か|
    |canXxxxXxxx|can_xxxx_xxxx|Boolean|xxxxが出来るか否か|
    |fileExists|file_exists|Boolean|ファイルが存在するか否か|
    |getXxxx|get_xxxx|int \| String|xxxxの値を取得|
    |putXxxx|put_xxxx|int \| String|xxxxに値を設定|
    |generateXxxx|generate_xxxx|void, XxxxException|xxxxの生成処理|
    |removeXxxx|remove_xxxx|void, XxxxException|xxxxの除去処理|


## 2. Java 

Eclipse のプラグイン “Checkstyle” のチェックに合格することが望ましい。<br>

* 80文字から120文字で、改行を入れるよう工夫する。
* パッケージ名は小文字とする。
* クラス名、ファイル名は、アッパーキャメルケースとする。
* クラスメソッド名、変数名は、キャメルケースとする。
* 定数名は、大文字とアンダースコアとする。
* 段下げは、タブを使用し、空白 4文字分とする。
* 共通変数名は、“ConstUtil.java” に定義する。
* 起動時の可変値（例えば、ポート番号）は、ファイル “application.properties” に定義し、“PropertyUtil.java” を通じて値を取り出す。
* return は省略不可とする。
* for、while、do-while、if、else、switch、try、catch の “{” と “}” は、省略不可とする。
* 全体的な書き方（例えば、空白の空け方、“} else {” の書き方）：
    ```
    /**
     * Xxxx Utility
     *   It processes common xxxx.
     */
    public class XxxxUtil {

        private int MAX_PASSWORD_LENGTH = 8

        /*
         * Check Password
         */
        public static void CheckPassword(String password) throw XxxxException {

            // Check password length.
            if (! password.length()) {
                ...;
            } else if (password.length() > MAX_PASSWORD_LENGTH) {
                ...;
            } else {
                ...;
            }

            // Check password letters.
            for (int i = 0; i < password.length(); i++) {
                ...;
            }

            // Check the xxxx.
            try {
                ...;
            } catch(Exception ex) {
                throw new XxxxException(ex.getMessage());
            }

            return;
        }
    }
    ```
    クラスメソッド、for、while、do-while、if、else、switch、catch の “(”の前に空白を空け、“(”の後ろには空白を空けない。また、“)”の前には空白を空けない。<br>
    クラスメソッド、for、while、do-while、if、else、switch、try、catch の “{”の前に空白を空ける。<br>
    代入演算子、算術演算子、比較演算子の前後には空白を空ける。<br>
    単項算術演算子（“++” 等）は、空白を空けない。<br>
    コンマ“,”の後ろに空白を空ける<br>

## 3. Python 

PEP（Python Enhancement Proposal）に準拠することが望ましい。PyCharm は、PEP 準拠チェックを行ってくれる。<br>
<https://pep8-ja.readthedocs.io/ja/latest/><br>

* 80文字から120文字で、改行を入れるよう工夫する。
* 段下げは、空白 4文字を使用する。
* クラス名は、アッパーキャメルケースとする。
* 関数名、クラスメソッド名、変数名は、スネークケースとする。
* 定数名は、大文字とアンダースコアとする。
* return は、省略不可とする。
* 全体的な書き方（例えば、空白の空け方）：
    ```
    # Constant
    MAX_PASSWORD_LENGTH = 8


    # Main
    def main():
        ...
        return


    # Check Password
    def check_password(password: str) -> None:

        # Check password length.
        if not password.len():
            ...
        elif password.len() > MAX_PASSWORD_LENGTH:
            ...
        else:
            ...

        # Check password letters.
        for i in range(0, password.len()):
            ...

        # Check the xxxx.
        try:
            ...
        except Exception as ex:
            raise XxxxException(ex)

        return


    # Goto Main
    if __name__ == '__main__':
        main()
    ```
    “:” の前に空白を空けない。<br>
    代入演算子、算術演算子、比較演算子の前後には空白を空ける。<br>
    関数やクラスの引数は、アノテーション “: ” を使用して型を明確にする。<br>
    関数やクラスには、アノテーション “ -> ” を使用して型を明確にする。<br>
    コンマ“,”の後ろに空白を空ける<br>
    関数やクラスの前後には、2つの改行を空ける。<br>

## 4. HTML（HTML テンプレートを含む）

* 段下げは、空白 2文字分とする。
* タグは、小文字を使用する。
* 閉じタグを省略する（例えば、“&lt;input ... /&gt;”）場合は、“/&gt;”の前に空白を空ける。

## 5. SQL

* 80文字から120文字で、改行を入れるよう工夫する。
* 段下げは、タブを使用し、空白 4文字分とする。
* 段下げの入れ方について、例えば、SELECT 文において、FROM、WHERE、GROUP BY、HAVING、ORDER BY の行ごとに段下げをする。
* 表名、列名等は、全て大文字またはアンダースコアとする。スネークケースとする。（プロジェクト判断とする）
* SELECT 文の選択リストに “*” を使用しない。
* INSERT 文の挿入列リストを省略しない。
* 複数表のジョインなどにより SELECT 選択リストや WHERE 条件などが複雑になる場合は、FROM に別表名を指定し、列名は“別表名.列名”とする。

<div style="text-align: right;">- 以上 -</div>
