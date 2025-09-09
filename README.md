
## 🚀 Como Executar

1. Edite o arquivo `exemplo02.json` com a definição do seu NFA.
2. Execute o script `main.py`.
3. O DFA será salvo em `dfa.json` e impresso no terminal.




### 🔍 `read_nfa(file_path)`
```python
with open(file_path, 'r') as f:
    return json.load(f)
```
- Lê o arquivo JSON contendo o NFA e transforma em um dicionário Python.

---

### 🔢 `powerset(iterable)`
```python
s = list(iterable)
return list(chain.from_iterable(combinations(s, r) for r in range(len(s) + 1)))
```
- Gera todos os subconjuntos possíveis de um conjunto (não usado diretamente no fluxo principal).

---

### 🔄 `nfa_to_dfa(nfa)`
- Converte o NFA para DFA usando o algoritmo de subconjuntos.
- Cria estados compostos a partir de conjuntos de estados do NFA.
- Gera transições determinísticas.
- Marca estados finais que contêm pelo menos um estado final do NFA.

---

### 🧱 `complete_dfa(dfa, sink_name="Z")`
- Garante que o DFA seja completo.
- Adiciona transições faltantes para um estado poço `"Z"`.
- Cria transições autoabsorventes para o estado poço.

---

### 🔠 `rename_states(dfa)`
- Renomeia os estados do DFA para letras (A, B, C...) ou nomes genéricos (S0, S1...).
- Atualiza nomes em transições, estado inicial e estados finais.

---

### 💾 `save_dfa(dfa, file_path)`
- Salva o DFA convertido em um arquivo JSON formatado.

---

### 📊 `print_dfa(dfa)`
- Exibe no terminal os dados do DFA.
- Imprime uma tabela de transições organizada por estado e símbolo.

---

### 🚀 Bloco principal
```python
if __name__ == "__main__":
```
- Executa o fluxo completo:
  - Lê o NFA.
  - Converte para DFA.
  - Completa o DFA.
  - Renomeia os estados.
  - Salva e imprime o resultado.

---
