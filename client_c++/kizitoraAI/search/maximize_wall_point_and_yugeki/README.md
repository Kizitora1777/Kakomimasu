# 城壁ポイント貪欲 + 遊撃

## 概要

このソルバは大きく二つのグループに分かれる

1. 周囲八近傍のうち最もポイントの高いマスを取りに行くグループ
2. 遊撃(陣地ポイントの獲得するエージェント, 相手の陣地完成を防ぐエージェントなど)

1についてはマスを踏むだけでなく、条件付きで敵のマスを削除するという動きも行う。
2はまだ具体的には決まってないが、得点データをもとによさげな陣地候補をいくつか見つけ、そこを優先的に囲む動きをしたり、相手の陣地完成を一歩手前で防ぐ動きをする。

## 考察

+ 基本的には hill_climbing のような城壁貪欲に加えて、遊撃を追加して戦略に含みを持たせる形にする。このようにすることで、戦略を用いた立ち回りを実現できるようになる
+ hill_climbingは完全な運ゲーだったのに対して、遊撃枠を作ることで一発逆転や防御といった立ち回りが出来るようになり、勝率を上げることができるのではないか
+ 城壁ポイント取りに行くグループはビームサーチで実装した方がよさそう。貪欲だと一手先しか見ていないため