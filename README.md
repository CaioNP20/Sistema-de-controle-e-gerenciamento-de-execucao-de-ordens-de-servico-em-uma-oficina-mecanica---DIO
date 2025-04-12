<h1>Modelagem de Banco de Dados - Sistema de Oficina Mecânica</h1>
  
Este documento descreve a modelagem do banco de dados para um sistema de gerenciamento de ordens de serviço (OS) em uma oficina mecânica.

## 🔗 Relacionamentos e Cardinalidades

| Relacionamento               | Tipo  | Descrição                                          |
|------------------------------|-------|----------------------------------------------------|
| `PESSOA → CLIENTE`           | `1:1` | Uma pessoa pode ser um cliente (opcional).         |
| `PESSOA → MECÂNICO`          | `1:1` | Uma pessoa pode ser um mecânico (opcional).        |
| `CLIENTE → VEÍCULO`          | `1:N` | Um cliente pode ter vários veículos.               |
| `VEÍCULO → ORDEM_SERVICO`    | `1:N` | Um veículo pode ter várias OS.                     |
| `ORDEM_SERVICO → SERVIÇO`    | `N:M` | Uma OS pode ter vários serviços (e vice-versa).    |
| `ORDEM_SERVICO → PEÇA`       | `N:M` | Uma OS pode usar várias peças (e vice-versa).      |
| `EQUIPE → ORDEM_SERVICO`     | `1:N` | Uma equipe pode atender várias OS.                 |
| `EQUIPE → MECÂNICO`          | `1:N` | Uma equipe pode ter vários mecânicos.              |

### Legenda:
- **`1:1`**: Um para Um
- **`1:N`**: Um para Muitos
- **`N:M`**: Muitos para Muitos

Além disso, o tipo ENUM presente em ORDEM DE SERVIÇO é para dizer se é 'Conserto' ou 'Revisão'.
