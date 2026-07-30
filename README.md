# Quantum Field Theory Term Paper: AI Chat Logs & Mathematical Explanations

An official public archive containing the complete conversation logs, **unabridged draft PDF**, and **40 detailed mathematical explanation documents** generated in collaboration with AI (Antigravity / Gemini) during the preparation of the **Quantum Field Theory I** term paper.

---

## 📄 Unabridged Draft PDF & Browser Notice

* **Unabridged Draft PDF**: [`Kokin_Cho_QFT_term_paper_draft.pdf`](./Kokin_Cho_QFT_term_paper_draft.pdf)  
  Contains line-by-line intermediate algebraic derivations, detailed Feynman diagram combinatorics, and expanded mathematical proofs omitted from the concise final report.

> [!WARNING]
> **Safari Browser PDF Preview Notice**  
> GitHub's embedded PDF viewer may fail to render `Kokin_Cho_QFT_term_paper_draft.pdf` on **Apple Safari** due to browser-specific PDF.js engine limitations (throwing an `Error loading PDF page number 1` message).  
> **If you encounter a blank or error screen on Safari, please try using another browser (Google Chrome, Firefox, Microsoft Edge, etc.) or click the "Download raw" button to view the PDF locally.**

---

## 📁 Repository Structure

```
qft-report-explanations/
├── README.md                           # Overview and table of contents
├── Kokin_Cho_QFT_term_paper_draft.pdf  # Unabridged draft PDF with full derivations
├── chat_logs/                          # Full conversation logs (5 files)
│   ├── log1_part_A_1.md
│   ├── log2_part_A_2.md
│   ├── log3_part_B_1.md
│   ├── log4_part_B_2.md
│   └── log5_part_B_3.md
└── explanations/                       # Detailed mathematical explanation documents (40 files)
```

---

## 📜 Complete Document Index

### 1. Conversation Logs (`chat_logs/`)
* [`log1_part_A_1.md`](./chat_logs/log1_part_A_1.md): Dialogue and derivations for Part A, Questions 1–3 (Dirac field bilinears and Lorentz transformations).
* [`log2_part_A_2.md`](./chat_logs/log2_part_A_2.md): Further discussion and refinement on Part A.
* [`log3_part_B_1.md`](./chat_logs/log3_part_B_1.md): Path integral quantization, free/interacting generating functionals, and Feynman rules for complex scalar field $\lambda(\phi^*\phi)^2$ (Part B, Q1 subquestions 1–5).
* [`log4_part_B_2.md`](./chat_logs/log4_part_B_2.md): Momentum-space Feynman rules, 2-point self-energy, physical mass shift, and 4-point vertex coupling renormalization (Part B, Q1 subquestions 6–8).
* [`log5_part_B_3.md`](./chat_logs/log5_part_B_3.md): Rigorous Wick rotation, complex $D$-plane, 't Hooft-Veltman dimensional regularization, and isolated Gamma function poles (Part B, Q1 subquestions 9–10).

---

### 2. Topic-Specific Explanation Guides (`explanations/`)

#### 🔹 Wick Rotation, Dimensional Regularization & Renormalization
* [`partB_Q1_question9_wick_rotation_rigorous_explanation.md`](./explanations/partB_Q1_question9_wick_rotation_rigorous_explanation.md): Rigorous proof of $i\epsilon$ pole factorization, Cauchy contour rotation, and imaginary-time continuation showing exact cancellation of $i^2 = -1$ with the denominator minus sign.
* [`partB_Q1_complex_D_plane_dimensional_regularization_explanation.md`](./explanations/partB_Q1_complex_D_plane_dimensional_regularization_explanation.md): Conceptual and mathematical foundation of the complex $D$-plane in 't Hooft-Veltman dimensional regularization and physical interpretation of isolated Gamma poles.
* [`partB_Q1_vertex_function_explicit_integration_guide.md`](./explanations/partB_Q1_vertex_function_explicit_integration_guide.md): Explicit integration of the 1-loop bubble $V(q)$ in $D = 4 - 2\epsilon$, Laurent expansion of $\Gamma(\epsilon)$, $1/\epsilon$ counterterm absorption, and derivation of the finite observable $\ln(q^2/m^2)$ amplitude.
* [`partB_Q1_question10_required_knowledge_guide.md`](./explanations/partB_Q1_question10_required_knowledge_guide.md): Comprehensive guide for subquestion (10) covering Gamma function isolated poles, Feynman parametrization, Schwinger parameters, and Kinematics at the Mandelstam Symmetry Point.
* [`partB_Q1_direct_euclidean_propagator_derivation.md`](./explanations/partB_Q1_direct_euclidean_propagator_derivation.md): Three direct derivations of the Euclidean propagator $G_0^E(p_E) = \frac{1}{p_E^2+m_0^2}$ without relying on Wick rotation (Elliptic Differential Equations, Gaussian Path Integrals, and Zero-Temperature Matsubara Limits).
* [`partB_Q1_renormalized_coupling_concept_explanation.md`](./explanations/partB_Q1_renormalized_coupling_concept_explanation.md): Quantitative relationship between the bare coupling $\lambda_0$ and physical renormalized coupling $g \coloneqq \frac{1}{4}\Gamma^{(4)}(0,0,0,0)$.
* [`partB_Q1_coupling_vs_amplitude_logical_bridge.md`](./explanations/partB_Q1_coupling_vs_amplitude_logical_bridge.md): Logical bridge connecting Lagrangian interaction parameters to physical 4-point scattering amplitudes.
* [`partB_Q1_propagator_notation_clarification.md`](./explanations/partB_Q1_propagator_notation_clarification.md): Clarification of propagator notations ($G_0(p)$ in momentum space vs. $G_0(0)$ at coincidence limit $x-y=0$) and Fourier transform conventions.
* [`partB_Q1_question7_deep_explanation.md`](./explanations/partB_Q1_question7_deep_explanation.md): Physical explanation of mass renormalization upwards ($m > m_0$) via quantum mechanical energy-level shifts and virtual particle cloud dressing (effective inertia).
* [`partB_Q1_question6_coefficients_and_diagrams.md`](./explanations/partB_Q1_question6_coefficients_and_diagrams.md): Derivation of 1PI 4-point loop channel coefficients ($8\lambda^2$ for $s$-channel, $16\lambda^2$ for $t$- and $u$-channels) and symmetry factors for complex scalar $\lambda(\phi^*\phi)^2$.
* [`partB_Q1_question6_coefficient_derivation_explanation.md`](./explanations/partB_Q1_question6_coefficient_derivation_explanation.md): Detailed combinatorial verification aligning perturbation expansion factors $1/2!$ with Wick contraction counts.
* [`partB_Q1_thorough_review_and_diagram_analysis.md`](./explanations/partB_Q1_thorough_review_and_diagram_analysis.md): Comprehensive review and diagrammatic analysis of Part B Question 1.

#### 🔹 Path Integrals, Generating Functionals & Feynman Rules
* [`generating_functional_explanation.md`](./explanations/generating_functional_explanation.md): First-principles derivation of the generating functional $Z_0[J, J^*]$ for free scalar fields.
* [`interacting_generating_functional_explanation.md`](./explanations/interacting_generating_functional_explanation.md): Derivation of the full interacting functional $Z[J, J^*]$ via functional differential operator factorisation.
* [`all_generating_functional_representations_master_guide.md`](./explanations/all_generating_functional_representations_master_guide.md): Master guide on all equivalent representations of generating functionals in QFT.
* [`feynman_rules_derivation_explanation.md`](./explanations/feynman_rules_derivation_explanation.md): Step-by-step derivation of position and momentum space Feynman rules.
* [`feynman_rules_conceptual_origin_explanation.md`](./explanations/feynman_rules_conceptual_origin_explanation.md): Conceptual origins of Feynman propagators, vertices, and symmetry factors.
* [`vacuum_diagram_cancellation_and_normalization.md`](./explanations/vacuum_diagram_cancellation_and_normalization.md): Proof of exact cancellation of disconnected vacuum bubble diagrams via path integral normalization $Z[0,0]$.
* [`wick_theorem_guide.md`](./explanations/wick_theorem_guide.md): Comprehensive guide on Wick's Theorem for operator T-products and path integral contractions.
* [`vev_derivation_explanation.md`](./explanations/vev_derivation_explanation.md): Derivation of vacuum expectation values (VEVs) and $U(1)$ charge conservation constraints.
* [`qft_first_principles_and_problem_solving_map.md`](./explanations/qft_first_principles_and_problem_solving_map.md): First-principles physics roadmap for quantum field theory problem solving.

#### 🔹 General QFT Topics & Renormalization Formalism
* [`math_explanation_20260715_renormalization.md`](./explanations/math_explanation_20260715_renormalization.md): Mathematical and physical principles of field theory renormalization.
* [`math_explanation_20260715_renormalization_calculation.md`](./explanations/math_explanation_20260715_renormalization_calculation.md): Practical techniques for evaluating loop integrals and extracting counterterms.
* [`math_explanation_20260715_renormalization_gamma5.md`](./explanations/math_explanation_20260715_renormalization_gamma5.md): Treatment of Dirac $\gamma_5$ matrices and chiral structures in dimensional regularization.
* [`math_explanation_20260715_renormalization_kinematics.md`](./explanations/math_explanation_20260715_renormalization_kinematics.md): Kinematic variables, Mandelstam invariants, and momentum conservation in loop diagrams.
* [`math_explanation_20260715_renormalization_lsz_tree.md`](./explanations/math_explanation_20260715_renormalization_lsz_tree.md): LSZ reduction formula and connection to tree-level scattering amplitudes.
* [`math_explanation_20260715_renormalization_phi.md`](./explanations/math_explanation_20260715_renormalization_phi.md): Wavefunction renormalization constant $Z_\phi$ and field rescaling.
* [`math_explanation_20260715_renormalization_residue.md`](./explanations/math_explanation_20260715_renormalization_residue.md): Propagator pole residue interpretation and physical particle state normalization.
* [`math_explanation_20260715_renormalization_virtual.md`](./explanations/math_explanation_20260715_renormalization_virtual.md): Role of virtual particle loops in loop corrections.
* [`gellmann_low_interaction_picture_explanation.md`](./explanations/gellmann_low_interaction_picture_explanation.md): Gell-Mann & Low Theorem and adiabatic switching of interaction Hamiltonians.
* [`time_evolution_operator_identity_proof.md`](./explanations/time_evolution_operator_identity_proof.md): Proof of time-evolution operator identities in the interaction picture.
* [`concrete_diagram_math_mapping_explanation.md`](./explanations/concrete_diagram_math_mapping_explanation.md): Explicit mapping between Feynman diagrammatic topologies and mathematical expressions.
* [`position_to_momentum_space_conversion.md`](./explanations/position_to_momentum_space_conversion.md): Fourier transformation techniques from position space to momentum space.
* [`propagator_notation_comparison.md`](./explanations/propagator_notation_comparison.md): Comparative reference for propagator notation conventions across major QFT textbooks (Peskin & Schroeder, Srednicki, Fradkin).
* [`qft_partB_q1_5_solution_explanation.md`](./explanations/qft_partB_q1_5_solution_explanation.md): Solution breakdown for Part B Question 1 (5).
* [`question5_audit_and_solution_plan.md`](./explanations/question5_audit_and_solution_plan.md): Audit and plan for diagrammatic multiplicity verification.
* [`question6_problem_breakdown.md`](./explanations/question6_problem_breakdown.md): Problem breakdown for Question 6.
* [`tikz_embedding_best_practice.md`](./explanations/tikz_embedding_best_practice.md): Best practices for compiling and embedding TikZ Feynman diagrams in LaTeX documents.
* [`tikz_feynman_loop_gallery.md`](./explanations/tikz_feynman_loop_gallery.md): Gallery of TikZ Feynman loop diagrams.
