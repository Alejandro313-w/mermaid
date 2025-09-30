flowchart TD
  A[Materia prima] --> A1[Propileno + NH3 + O2 (ammoxidación)]
  A1 --> B[Acrilonitrilo (principal)]
  A1 --> C[Acetonitrilo (subproducto)]
  D[Otra vía industrial] --> E[Acetamida]
  E --> F[Deshidratación (P2O5 / POCl3)]
  F --> C

  subgraph Obtencion_labo
    G[Compra solvente grado laboratorio] --> H[Uso directo]
    I[Deshidratación de acetamida en lab] --> C2[Acetonitrilo crude-Lab]
    C2 --> Pur[Destilación & Secado]
    Pur --> H
  end

  C --> PurIndustrial[Destilación fraccionada y secado]
  PurIndustrial --> Uses[Almacenamiento para usos industriales y laboratorio]

  Uses --> L1[Usos en laboratorio]
  L1 --> |HPLC| U1[Mobile phase]
  L1 --> |Reacción| U2[Solvente para sintesis]
  L1 --> |Electroquímica| U3[Electrolito / investigación]

  %% RECUPERACION
  Uses --> R[Generación de residuos]
  R --> S[Segregación / etiquetado]
  S --> T[Evaluación: recuperable?]
  T -- Sí --> U[Pretratamiento (filtrado/decantación)]
  U --> V[Destilación a vacío]
  V --> W[Secado (tamices) + Carbón]
  W --> Q[Análisis (GC/HPLC/KF)]
  Q --> |Cumple| Reuse[Reintroducir a inventario]
  Q --> |No cumple| Dispose[Disposición final]

  T -- No --> Dispose

  Dispose --> X[Gestor autorizado / incineración controlada]
  X --> End[Registro & documentación]

  %% notas de seguridad
  style A fill:#f9f,stroke:#333,stroke-width:1px
  classDef warn fill:#ffe6e6,stroke:#cc0000;
  class S,T,Dispose warn

