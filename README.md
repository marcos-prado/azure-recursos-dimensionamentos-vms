# Configurando Recursos e Dimensionamentos em Máquinas Virtuais na Azure  

![Azure Virtual Machines](/images/virtual-machines.png)  

## Introdução  
Configurar adequadamente os recursos e dimensionar máquinas virtuais (VMs) no Microsoft Azure é essencial para garantir desempenho, disponibilidade e custo-eficiência. Este guia aborda os principais conceitos e práticas recomendadas para dimensionar VMs na Azure.  

---

## 1. Escolhendo a Série de VM Adequada  
A Azure oferece diversas séries de VMs, cada uma otimizada para cargas de trabalho específicas:  

| Série         | Recomendação de Uso                      | Exemplo de Caso de Uso          |  
|---------------|------------------------------------------|---------------------------------|  
| **Série B**   | Cargas intermitentes (dev/test)          | Servidores de desenvolvimento   |  
| **Série D**   | Propósito geral (CPU + RAM balanceados)  | Aplicações empresariais         |  
| **Série F**   | Computação otimizada (alta CPU)          | Processamento batch             |  
| **Série E**   | Memória otimizada (alta RAM)             | Bancos de dados, SAP HANA       |  
| **Série N**   | GPU (processamento gráfico/IA)           | Renderização, machine learning  |  

📌 **Dica:** Utilize a [Calculadora de Preços da Azure](https://azure.microsoft.com/pricing/calculator/) para comparar custos.  

---

## 2. Configurando CPU, Memória e Armazenamento  
Ao criar uma VM, ajuste:  

- **vCPUs:** Número de núcleos virtuais.  
- **Memória RAM:** Definida conforme a série da VM.  
- **Armazenamento:**  
  - **SSD Premium** (alta performance)  
  - **HDD Standard** (custo-benefício)  

📌 **Dica:** Utilize **discos gerenciados** para maior confiabilidade.  

---

## 3. Escalando VMs (Vertical e Horizontal)  

### 🔄 Escalamento Vertical (Aumentar Recursos da VM)  
- **O que faz:** Altera o tamanho da VM (ex.: `D2s_v3` → `D4s_v3`).  
- **Requer:** Reinicialização.  

**Passos:**  
1. No portal Azure, vá em **Máquinas Virtuais**.  
2. Selecione a VM e clique em **Tamanho**.  
3. Escolha um novo tamanho e reinicie.  

### ↔️ Escalamento Horizontal (Adicionar Mais VMs)  
![VMSS Autoscale](/images/vmss.png)
- **Usa:** Conjuntos de Escala de Máquinas Virtuais (**VMSS**).  
- **Indicado para:** Aplicações distribuídas e balanceamento de carga.  

**Como configurar VMSS:**

1. Crie um **Virtual Machine Scale Set** no portal Azure.  
2. Defina regras de *autoscale* baseadas em métricas (CPU, memória).  

---

## 4. Otimizando Custos  

| Método               | Vantagem                              | Melhor Caso de Uso              |  
|----------------------|---------------------------------------|----------------------------------|  
| **Spot VMs**         | Até 90% de desconto                   | Workloads tolerantes a falhas    |  
| **Instâncias Reservadas** | Economia de longo prazo (até 72%) | Cargas de trabalho contínuas     |  

📌 **Dica:** Use **Azure Advisor** para recomendações de otimização.  

---

## 5. Monitoramento e Ajuste Contínuo  
- **Ferramentas:**  
  - **Azure Monitor** (métricas de desempenho).  
  - **Alertas** (notificações para uso alto de CPU/RAM).  

---

## Conclusão  
Para dimensionar VMs na Azure com eficiência:  
✅ **Analise** a carga de trabalho.  
✅ **Escolha** a série correta de VM.  
✅ **Use** autoscale (VMSS) para flexibilidade.  
✅ **Monitore** com Azure Monitor.  

🔗 **Links Úteis:**  
- [Documentação Oficial Azure VMs](https://docs.microsoft.com/azure/virtual-machines/)  
- [Calculadora de Preços Azure](https://azure.microsoft.com/pricing/calculator/)  
