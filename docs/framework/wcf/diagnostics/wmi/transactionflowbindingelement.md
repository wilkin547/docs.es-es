---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: d0311837ebb8112d9492fb548492bcd3e10230e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54514579"
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="7666d-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="7666d-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="7666d-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="7666d-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7666d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7666d-104">Syntax</span></span>  
  
```csharp
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7666d-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="7666d-105">Methods</span></span>  
 <span data-ttu-id="7666d-106">La clase TransactionFlowBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="7666d-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7666d-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="7666d-107">Properties</span></span>  
 <span data-ttu-id="7666d-108">La clase TransactionFlowBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="7666d-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="7666d-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="7666d-109">IssuedTokens</span></span>  
 <span data-ttu-id="7666d-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="7666d-110">Data type: string</span></span>  
  
 <span data-ttu-id="7666d-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="7666d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7666d-112">Especifica el requisito para un encabezado de token de seguridad emitido (IssuedTokens de WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="7666d-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="7666d-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="7666d-113">TransactionProtocol</span></span>  
 <span data-ttu-id="7666d-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="7666d-114">Data type: string</span></span>  
  
 <span data-ttu-id="7666d-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="7666d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7666d-116">El protocolo de transacciones utilizado por el servicio para fluir las transacciones.</span><span class="sxs-lookup"><span data-stu-id="7666d-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="7666d-117">Transacciones</span><span class="sxs-lookup"><span data-stu-id="7666d-117">Transactions</span></span>  
 <span data-ttu-id="7666d-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="7666d-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="7666d-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="7666d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7666d-120">Indica si se admite la transacción entrante.</span><span class="sxs-lookup"><span data-stu-id="7666d-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7666d-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7666d-121">Requirements</span></span>  
  
|<span data-ttu-id="7666d-122">MOF</span><span class="sxs-lookup"><span data-stu-id="7666d-122">MOF</span></span>|<span data-ttu-id="7666d-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="7666d-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7666d-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="7666d-124">Namespace</span></span>|<span data-ttu-id="7666d-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7666d-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7666d-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="7666d-126">See also</span></span>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
