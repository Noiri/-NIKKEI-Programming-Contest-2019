# NIKKEI-Programming-Contest-2019
## A問題
今回、緑昇格がかかっていたこともあり自分でもびっくりするほどテンパっていた。
簡単な問題であるはずなのに5分もかかってしまって悔しい。
テンパってる時は、どんなに簡単な問題でも一旦紙に書き出して見るのが良いと感じた。
```cpp
#include <bits/stdc++.h>
using namespace std;

int main(){
    int n, a, b;
    cin >> n >> a >> b;
    cout << min(a, b) << " " << max(0, b-(n-a)) << endl;
    return 0;
}
```

## B問題
もう少し速く実装したかった。
i番目の文字を比較して、2つ一緒ならばans+=1、3つ一緒ならばそのまま、全部異なるならばans+=2とすれば良い。
競技終了後に、もうちょっとシンプルに書けないか他人のコードを見てみたがc++だとこれが限界らしく、
まじか、if文減らしたいなぁ・・・とか考えてた。
そのあとにrubyのコード見たら短すぎてびびった。その内、スクリプト言語でも競プロやろうかな・・・？

```cpp
#include <bits/stdc++.h>
using namespace std;

int main(){
    int n;
    cin >> n;
    string a, b, c;
    cin >> a >> b >> c;
    int ans = 0;
    for(int i=0; i<n; i++){
        if(a[i] == b[i] && a[i] != c[i]) ans++;
        else if(a[i] == c[i] && a[i] != b[i]) ans++;
        else if(b[i] == c[i] && b[i] != a[i]) ans++;
        else if(a[i] != b[i] && a[i] != c[i] && b[i] != c[i]) ans += 2;
    }
    cout << ans << endl;
    return 0;
}
```

## C問題
これは、競技時間中いっぱい粘ってみたが解けなかった。解説読んで「うわー」ってなってた。
現在は、C問安定して通せるといいなと考えているので、この問題は勉強になった。

```cpp
#include <bits/stdc++.h>
using namespace std;

typedef long long ll;

int main(){
    int n;
    cin >> n;
    vector<ll> v(n);
    ll ans = 0;
    for(int i=0; i<n; i++){
        ll a, b;
        cin >> a >> b;
        v[i] = a + b;
        ans -= b;
    }
    sort(v.rbegin(), v.rend());
    for(int i=0; i<n; i+=2) ans += v[i];
    cout << ans << endl;
    return 0;
}
```

## D問題
そのうち書く

## まとめ
C問通せなかったし、A,Bも遅かったので満足のいく結果ではなかった。
一応レートは上がったが、次は満足のいく結果を残せるといいな。
そのためには、まずC問埋め終わらせないと...
