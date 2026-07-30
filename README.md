# Quantum Field Theory Term Paper AI Explanations & Logs

場の量子論（Quantum Field Theory I）の期末レポートを作成するにあたり、AI（Antigravity / Gemini）との対話を通じて生成された**全会話ログ**および**詳細解説 Markdown ドキュメント**の公認アーカイブ・リポジトリです。

---

## 📁 リポジトリ構造

```
qft-report-explanations/
├── README.md                 # 本ファイル（目次・概要）
├── chat_logs/                # AIとの全対話ログ（全 5 ファイル）
│   ├── log1_part_A_1.md
│   ├── log2_part_A_2.md
│   ├── log3_part_B_1.md
│   ├── log4_part_B_2.md
│   └── log5_part_B_3.md
└── explanations/             # 生成された個別テーマの詳細解説ドキュメント（全 40 ファイル）
```

---

## 📜 収録ファイル一覧

### 1. 会話ログ (`chat_logs/`)
* [`log1_part_A_1.md`](./chat_logs/log1_part_A_1.md): Part A 問 1〜3 の対話・導出ログ
* [`log2_part_A_2.md`](./chat_logs/log2_part_A_2.md): Part A 発展・検討対話ログ
* [`log3_part_B_1.md`](./chat_logs/log3_part_B_1.md): Part B 第 1 問 (1)〜(5) 経路積分・ファインマンルール対話ログ
* [`log4_part_B_2.md`](./chat_logs/log4_part_B_2.md): Part B 第 1 問 (6)〜(8) 運動量空間・質量の繰り込み・結合定数の再規格化対話ログ
* [`log5_part_B_3.md`](./chat_logs/log5_part_B_3.md): Part B 第 1 問 (9)〜(10) Wick回転・次元正則化・複素 $D$ 平面・Laurent展開対話ログ

---

### 2. テーマ別詳細解説ドキュメント (`explanations/`)

#### Part B 第 1 問 (Wick回転・繰り込み・次元正則化) 関連
* [`partB_Q1_question9_wick_rotation_rigorous_explanation.md`](./explanations/partB_Q1_question9_wick_rotation_rigorous_explanation.md): $i\epsilon$ の極の分解、Wick回転における $i^2=-1$ と符号消去ステップ、虚数時間解析接続の厳密証明
* [`partB_Q1_complex_D_plane_dimensional_regularization_explanation.md`](./explanations/partB_Q1_complex_D_plane_dimensional_regularization_explanation.md): なぜ複素次元平面 $D$ を考えるのか？次元正則化と孤立極（Isolated Poles）の物理的意味
* [`partB_Q1_vertex_function_explicit_integration_guide.md`](./explanations/partB_Q1_vertex_function_explicit_integration_guide.md): 4点頂点関数 $\Gamma^{(4)}$ の 1ループバブル積分 $V(q)$ の具体的な対数積分計算と繰り込みによる有限値導出
* [`partB_Q1_question10_required_knowledge_guide.md`](./explanations/partB_Q1_question10_required_knowledge_guide.md): 問(10)を解くためのガンマ関数 $\Gamma(z)$ の孤立極・Feynmanパラメタライズ・Symmetry Point の整理
* [`partB_Q1_direct_euclidean_propagator_derivation.md`](./explanations/partB_Q1_direct_euclidean_propagator_derivation.md): Wick回転を使わずにユークリッド空間で伝播関数 $G_0^E(p_E) = \frac{1}{p_E^2+m_0^2}$ を直接求める 3 つのアプローチ
* [`partB_Q1_renormalized_coupling_concept_explanation.md`](./explanations/partB_Q1_renormalized_coupling_concept_explanation.md): 相互作用の結合定数 $\lambda_0$ と繰り込まれた結合定数 $g = \frac{1}{4}\Gamma^{(4)}(0,0,0,0)$ の定量的関係
* [`partB_Q1_coupling_vs_amplitude_logical_bridge.md`](./explanations/partB_Q1_coupling_vs_amplitude_logical_bridge.md): ラグランジアンの結合定数と散乱振幅の論理的架け橋
* [`partB_Q1_propagator_notation_clarification.md`](./explanations/partB_Q1_propagator_notation_clarification.md): $G_0(p)$（運動量空間伝播関数）と $G_0(0)$（相対座標 $x-y=0$ の伝播関数）のノーテーションと位置空間からのフーリエ変換導出
* [`partB_Q1_question7_deep_explanation.md`](./explanations/partB_Q1_question7_deep_explanation.md): 質量の上方繰り込み（$m > m_0$）の量子力学的エネルギーシフトおよび仮想粒子クラウド（Dressing）による物理的説明
* [`partB_Q1_question6_coefficients_and_diagrams.md`](./explanations/partB_Q1_question6_coefficients_and_diagrams.md): 複素スカラー場 $\lambda(\phi^*\phi)^2$ における 1PI 4点ループ係数 ($8\lambda^2, 16\lambda^2, 16\lambda^2$) と対称因子の詳細
* [`partB_Q1_question6_coefficient_derivation_explanation.md`](./explanations/partB_Q1_question6_coefficient_derivation_explanation.md): 摂動展開因子 $1/2!$ と Wick 縮約数の整合性に関する係数導出
* [`partB_Q1_thorough_review_and_diagram_analysis.md`](./explanations/partB_Q1_thorough_review_and_diagram_analysis.md): Part B 第1問全小問の網羅的チェックとダイアグラム解析

#### 経路積分・生成汎関数・ファインマンルール基礎
* [`generating_functional_explanation.md`](./explanations/generating_functional_explanation.md): 自由スカラー場の生成汎関数の第一原理からの導出
* [`interacting_generating_functional_explanation.md`](./explanations/interacting_generating_functional_explanation.md): 相互作用スカラー場の生成汎関数と汎関数微分演算子のくくり出し
* [`all_generating_functional_representations_master_guide.md`](./explanations/all_generating_functional_representations_master_guide.md): 生成汎関数の全等価表現マスターガイド
* [`feynman_rules_derivation_explanation.md`](./explanations/feynman_rules_derivation_explanation.md): 生成汎関数からのファインマンルールの導出
* [`feynman_rules_conceptual_origin_explanation.md`](./explanations/feynman_rules_conceptual_origin_explanation.md): ファインマンルールの概念的起源
* [`vacuum_diagram_cancellation_and_normalization.md`](./explanations/vacuum_diagram_cancellation_and_normalization.md): 真空バブルダイアグラムの因子分解と完全相殺の証明
* [`wick_theorem_guide.md`](./explanations/wick_theorem_guide.md): ウィックの定理ガイド
* [`vev_derivation_explanation.md`](./explanations/vev_derivation_explanation.md): 真空期待値（VEV）の導出と荷電保護 $U(1)$ 対称性
* [`qft_first_principles_and_problem_solving_map.md`](./explanations/qft_first_principles_and_problem_solving_map.md): 場の量子論の第一原理と問題解決マップ

#### 再規格化・その他理論トピックス
* [`math_explanation_20260715_renormalization.md`](./explanations/math_explanation_20260715_renormalization.md): 繰り込みの数学的・物理的基礎
* [`math_explanation_20260715_renormalization_calculation.md`](./explanations/math_explanation_20260715_renormalization_calculation.md): 繰り込み計算の手引き
* [`math_explanation_20260715_renormalization_gamma5.md`](./explanations/math_explanation_20260715_renormalization_gamma5.md): $\gamma_5$ 行列と繰り込み
* [`math_explanation_20260715_renormalization_kinematics.md`](./explanations/math_explanation_20260715_renormalization_kinematics.md): 繰り込みの運動学（Kinematics）
* [`math_explanation_20260715_renormalization_lsz_tree.md`](./explanations/math_explanation_20260715_renormalization_lsz_tree.md): LSZ簡約公式とTreeレベル振幅
* [`math_explanation_20260715_renormalization_phi.md`](./explanations/math_explanation_20260715_renormalization_phi.md): 場の再規格化定数 $Z_\phi$
* [`math_explanation_20260715_renormalization_residue.md`](./explanations/math_explanation_20260715_renormalization_residue.md): 伝播関数の留数と物理的意味
* [`math_explanation_20260715_renormalization_virtual.md`](./explanations/math_explanation_20260715_renormalization_virtual.md): 仮想粒子の繰り込みへの寄与
* [`gellmann_low_interaction_picture_explanation.md`](./explanations/gellmann_low_interaction_picture_explanation.md): Gell-Mann & Low の定理と相互作用描像
* [`time_evolution_operator_identity_proof.md`](./explanations/time_evolution_operator_identity_proof.md): 時間発展演算子の等式証明
* [`concrete_diagram_math_mapping_explanation.md`](./explanations/concrete_diagram_math_mapping_explanation.md): ファインマン図形と数式の具象的マッピング
* [`position_to_momentum_space_conversion.md`](./explanations/position_to_momentum_space_conversion.md): 位置空間から運動量空間への変換
* [`propagator_notation_comparison.md`](./explanations/propagator_notation_comparison.md): 伝播関数の表記法比較
* [`qft_partB_q1_5_solution_explanation.md`](./explanations/qft_partB_q1_5_solution_explanation.md): Part B Q1 (5) 解答解説
* [`question5_audit_and_solution_plan.md`](./explanations/question5_audit_and_solution_plan.md): 問 5 の検証と解決プラン
* [`question6_problem_breakdown.md`](./explanations/question6_problem_breakdown.md): 問 6 の問題分解
* [`tikz_embedding_best_practice.md`](./explanations/tikz_embedding_best_practice.md): TikZ 画像の埋め込みベストプラクティス
* [`tikz_feynman_loop_gallery.md`](./explanations/tikz_feynman_loop_gallery.md): TikZ によるファインマン図形描画ギャラリー
