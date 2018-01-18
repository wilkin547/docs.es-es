---
title: Compatibilidad con transacciones
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 543ea3d1a0f767a10b36e040155e7e9304aca5a9
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="transaction-support"></a><span data-ttu-id="75602-102">Compatibilidad con transacciones</span><span class="sxs-lookup"><span data-stu-id="75602-102">Transaction Support</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="75602-103">admite tres modelos de transacción distintos.</span><span class="sxs-lookup"><span data-stu-id="75602-103"> supports three distinct transaction models.</span></span> <span data-ttu-id="75602-104">A continuación se enumeran estos modelos por orden de comprobaciones realizadas.</span><span class="sxs-lookup"><span data-stu-id="75602-104">The following lists these models in the order of checks performed.</span></span>  
  
## <a name="explicit-local-transaction"></a><span data-ttu-id="75602-105">Transacción local explícita</span><span class="sxs-lookup"><span data-stu-id="75602-105">Explicit Local Transaction</span></span>  
 <span data-ttu-id="75602-106">Cuando se llama a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, si la propiedad <xref:System.Data.Linq.DataContext.Transaction%2A> se establece en una transacción (`IDbTransaction`), la llamada a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> se ejecuta en el contexto de la misma transacción.</span><span class="sxs-lookup"><span data-stu-id="75602-106">When <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called, if the <xref:System.Data.Linq.DataContext.Transaction%2A> property is set to a (`IDbTransaction`) transaction, the <xref:System.Data.Linq.DataContext.SubmitChanges%2A> call is executed in the context of the same transaction.</span></span>  
  
 <span data-ttu-id="75602-107">Es su responsabilidad confirmar o revertir la transacción después de su correcta ejecución.</span><span class="sxs-lookup"><span data-stu-id="75602-107">It is your responsibility to commit or rollback the transaction after successful execution of the transaction.</span></span> <span data-ttu-id="75602-108">La conexión que corresponde a la transacción debe coincidir con la conexión utilizada para construir <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="75602-108">The connection corresponding to the transaction must match the connection used for constructing the <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="75602-109">Si se utiliza una conexión diferente, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="75602-109">An exception is thrown if a different connection is used.</span></span>  
  
## <a name="explicit-distributable-transaction"></a><span data-ttu-id="75602-110">Transacción distribuible explícita</span><span class="sxs-lookup"><span data-stu-id="75602-110">Explicit Distributable Transaction</span></span>  
 <span data-ttu-id="75602-111">Puede llamar a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] API (incluidos pero no limitados a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>) en el ámbito de un activo <xref:System.Transactions.Transaction>.</span><span class="sxs-lookup"><span data-stu-id="75602-111">You can call [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] APIs (including but not limited to <xref:System.Data.Linq.DataContext.SubmitChanges%2A>) in the scope of an active <xref:System.Transactions.Transaction>.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="75602-112">detecta que la llamada está en el ámbito de una transacción y no crea una nueva transacción.</span><span class="sxs-lookup"><span data-stu-id="75602-112"> detects that the call is in the scope of a transaction and does not create a new transaction.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="75602-113">También impide el cierre la conexión en este caso.</span><span class="sxs-lookup"><span data-stu-id="75602-113"> also avoids closing the connection in this case.</span></span> <span data-ttu-id="75602-114">Puede ejecutar consultas y el método <xref:System.Data.Linq.DataContext.SubmitChanges%2A> en el contexto de este tipo de transacción.</span><span class="sxs-lookup"><span data-stu-id="75602-114">You can perform query and <xref:System.Data.Linq.DataContext.SubmitChanges%2A> executions in the context of such a transaction.</span></span>  
  
## <a name="implicit-transaction"></a><span data-ttu-id="75602-115">Transacción implícita</span><span class="sxs-lookup"><span data-stu-id="75602-115">Implicit Transaction</span></span>  
 <span data-ttu-id="75602-116">Cuando se llama a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] comprueba si la llamada se encuentra en el ámbito de un <xref:System.Transactions.Transaction> o si la `Transaction` propiedad (`IDbTransaction`) está establecida en una transacción local iniciada por el usuario.</span><span class="sxs-lookup"><span data-stu-id="75602-116">When you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] checks to see whether the call is in the scope of a <xref:System.Transactions.Transaction> or if the `Transaction` property (`IDbTransaction`) is set to a user-started local transaction.</span></span> <span data-ttu-id="75602-117">Si no encuentra ninguna de estas transacciones, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] inicia una transacción local (`IDbTransaction`) y lo utiliza para ejecutar los comandos SQL generados.</span><span class="sxs-lookup"><span data-stu-id="75602-117">If it finds neither transaction, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] starts a local transaction (`IDbTransaction`) and uses it to execute the generated SQL commands.</span></span> <span data-ttu-id="75602-118">Cuando se han completado correctamente todos los comandos SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] confirma la transacción local y devuelve.</span><span class="sxs-lookup"><span data-stu-id="75602-118">When all SQL commands have been successfully completed, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] commits the local transaction and returns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75602-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="75602-119">See Also</span></span>  
 [<span data-ttu-id="75602-120">Información general</span><span class="sxs-lookup"><span data-stu-id="75602-120">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="75602-121">Colocación entre corchetes de envíos de datos utilizando transacciones</span><span class="sxs-lookup"><span data-stu-id="75602-121">How to: Bracket Data Submissions by Using Transactions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)
