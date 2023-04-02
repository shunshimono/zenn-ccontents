---
title: "SPAと対になるのはMPAで、SSRと対になるのはCSRなんだよという話"
emoji: "🌟"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["react", "nextjs"]
published: true
---

# 動機

- Next.js の技術を検討する上で、SPA と SSR が比較記事が多数存在しているおり、各所で認識の乖離を起こしていそうな雰囲気を感じた
- 自分の現場では Next.js を利用していて、SPA と SSR を比較する人が多かった

# SPA とは？

- SPA とはシングルページアプリケーション (Single Page Application) の略称
- 1 つの HTML ファイルで画面遷移を完結させ、動的に URL や画面内の要素を書き換えるアプリケーションのことを指す

# MPA とは？

- MPA とはマルチページアプリケーション（Multi-Page Application）の略称
- 各画面遷移ごとにファイルを要求するアプリケーションのこと

# SSR とは？

- SSR はサーバーサイドレンダリング (Server-Side Rendering)の略称
- SSR とは、サーバー上で JavaScript を実行し、API からデータを取得して、取得したデータをもとにサーバー側で HTML を生成する手法のこと

# CSR とは？

- CSR はクライアントサイドレンダリング（Client-Side Rendering）の略称
- CSR とは、ブラウザ上で JavaScript を実行し、API からデータを取得して、取得したデータをもとにクライアント側で HTML を生成する手法のこと

# SPA と対になるのは MPA で、SSR と対になるのは CSR

- SPA ⇄ MPA
- CSR ⇄ SSR

# Next.js を利用しているから SSR されるわけではない

- getServerSideProps を実行しない場合は、サーバー側での HTML レンダリングは行われず、クライアント側で CSR が行われる
- getServerSideProps を利用する場合は、サーバー側での HTML レンダリングが行われるため、SSR が実行される

# Next.js を利用しているから SPA になるわけではない

- Next.js を使用した場合でも、next/link を利用せずに a タグで画面遷移を行うと、クライアント側でのルーティングとならず、サーバー側に HTML ファイルを要求する
- そのため、next/link を利用しない場合は、クライアント側でのルーティングが行われず、画面遷移のたびにサーバー側に HTML ファイルを要求するマルチページアプリケーション (MPA) となる
