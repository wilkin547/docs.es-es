---
title: TransactionFlowBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4c65eb1689d1411cb9083967b9a29c946b7568b7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="0eead-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="0eead-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="0eead-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="0eead-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0eead-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0eead-104">Syntax</span></span>  
  
```  
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="0eead-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="0eead-105">Methods</span></span>  
 <span data-ttu-id="0eead-106">La clase TransactionFlowBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="0eead-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0eead-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="0eead-107">Properties</span></span>  
 <span data-ttu-id="0eead-108">La clase TransactionFlowBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="0eead-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="0eead-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="0eead-109">IssuedTokens</span></span>  
 <span data-ttu-id="0eead-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="0eead-110">Data type: string</span></span>  
  
 <span data-ttu-id="0eead-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="0eead-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0eead-112">Especifica el requisito para un encabezado de token de seguridad emitido (IssuedTokens de WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="0eead-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="0eead-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="0eead-113">TransactionProtocol</span></span>  
 <span data-ttu-id="0eead-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="0eead-114">Data type: string</span></span>  
  
 <span data-ttu-id="0eead-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="0eead-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0eead-116">El protocolo de transacciones utilizado por el servicio para fluir las transacciones.</span><span class="sxs-lookup"><span data-stu-id="0eead-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="0eead-117">Transacciones</span><span class="sxs-lookup"><span data-stu-id="0eead-117">Transactions</span></span>  
 <span data-ttu-id="0eead-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="0eead-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="0eead-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="0eead-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0eead-120">Indica si se admite la transacción entrante.</span><span class="sxs-lookup"><span data-stu-id="0eead-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0eead-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0eead-121">Requirements</span></span>  
  
|<span data-ttu-id="0eead-122">MOF</span><span class="sxs-lookup"><span data-stu-id="0eead-122">MOF</span></span>|<span data-ttu-id="0eead-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="0eead-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0eead-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="0eead-124">Namespace</span></span>|<span data-ttu-id="0eead-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0eead-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0eead-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="0eead-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
