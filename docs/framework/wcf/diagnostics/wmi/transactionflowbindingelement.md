---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: c2fb32c4c693cbfc487ce89b36f013398cbdb703
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485625"
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="bccc3-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="bccc3-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="bccc3-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="bccc3-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bccc3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bccc3-104">Syntax</span></span>  
  
```  
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bccc3-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="bccc3-105">Methods</span></span>  
 <span data-ttu-id="bccc3-106">La clase TransactionFlowBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="bccc3-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bccc3-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="bccc3-107">Properties</span></span>  
 <span data-ttu-id="bccc3-108">La clase TransactionFlowBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="bccc3-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="bccc3-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="bccc3-109">IssuedTokens</span></span>  
 <span data-ttu-id="bccc3-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bccc3-110">Data type: string</span></span>  
  
 <span data-ttu-id="bccc3-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bccc3-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bccc3-112">Especifica el requisito para un encabezado de token de seguridad emitido (IssuedTokens de WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="bccc3-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="bccc3-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="bccc3-113">TransactionProtocol</span></span>  
 <span data-ttu-id="bccc3-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bccc3-114">Data type: string</span></span>  
  
 <span data-ttu-id="bccc3-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bccc3-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bccc3-116">El protocolo de transacciones utilizado por el servicio para fluir las transacciones.</span><span class="sxs-lookup"><span data-stu-id="bccc3-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="bccc3-117">Transacciones</span><span class="sxs-lookup"><span data-stu-id="bccc3-117">Transactions</span></span>  
 <span data-ttu-id="bccc3-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="bccc3-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="bccc3-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bccc3-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bccc3-120">Indica si se admite la transacción entrante.</span><span class="sxs-lookup"><span data-stu-id="bccc3-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bccc3-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bccc3-121">Requirements</span></span>  
  
|<span data-ttu-id="bccc3-122">MOF</span><span class="sxs-lookup"><span data-stu-id="bccc3-122">MOF</span></span>|<span data-ttu-id="bccc3-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="bccc3-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bccc3-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="bccc3-124">Namespace</span></span>|<span data-ttu-id="bccc3-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="bccc3-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bccc3-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="bccc3-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
