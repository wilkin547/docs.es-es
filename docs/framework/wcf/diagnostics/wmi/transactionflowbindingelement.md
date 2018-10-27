---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: 027ace6ea9fc2a0e5ce63efa84e1a49c0ed2cd0a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188032"
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="ad3ff-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="ad3ff-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="ad3ff-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="ad3ff-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad3ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad3ff-104">Syntax</span></span>  
  
```csharp
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ad3ff-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ad3ff-105">Methods</span></span>  
 <span data-ttu-id="ad3ff-106">La clase TransactionFlowBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="ad3ff-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ad3ff-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ad3ff-107">Properties</span></span>  
 <span data-ttu-id="ad3ff-108">La clase TransactionFlowBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="ad3ff-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="ad3ff-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="ad3ff-109">IssuedTokens</span></span>  
 <span data-ttu-id="ad3ff-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="ad3ff-110">Data type: string</span></span>  
  
 <span data-ttu-id="ad3ff-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ad3ff-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad3ff-112">Especifica el requisito para un encabezado de token de seguridad emitido (IssuedTokens de WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="ad3ff-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="ad3ff-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="ad3ff-113">TransactionProtocol</span></span>  
 <span data-ttu-id="ad3ff-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="ad3ff-114">Data type: string</span></span>  
  
 <span data-ttu-id="ad3ff-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ad3ff-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad3ff-116">El protocolo de transacciones utilizado por el servicio para fluir las transacciones.</span><span class="sxs-lookup"><span data-stu-id="ad3ff-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="ad3ff-117">Transacciones</span><span class="sxs-lookup"><span data-stu-id="ad3ff-117">Transactions</span></span>  
 <span data-ttu-id="ad3ff-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="ad3ff-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="ad3ff-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ad3ff-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad3ff-120">Indica si se admite la transacción entrante.</span><span class="sxs-lookup"><span data-stu-id="ad3ff-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad3ff-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ad3ff-121">Requirements</span></span>  
  
|<span data-ttu-id="ad3ff-122">MOF</span><span class="sxs-lookup"><span data-stu-id="ad3ff-122">MOF</span></span>|<span data-ttu-id="ad3ff-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ad3ff-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ad3ff-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="ad3ff-124">Namespace</span></span>|<span data-ttu-id="ad3ff-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ad3ff-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ad3ff-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad3ff-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
