---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: a58d5620abbb636480ceea3020552246ae284842
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641689"
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="15e54-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="15e54-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="15e54-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="15e54-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15e54-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15e54-104">Syntax</span></span>  
  
```csharp
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="15e54-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="15e54-105">Methods</span></span>  
 <span data-ttu-id="15e54-106">La clase TransactionFlowBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="15e54-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="15e54-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="15e54-107">Properties</span></span>  
 <span data-ttu-id="15e54-108">La clase TransactionFlowBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="15e54-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="15e54-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="15e54-109">IssuedTokens</span></span>  
 <span data-ttu-id="15e54-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="15e54-110">Data type: string</span></span>  
  
 <span data-ttu-id="15e54-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="15e54-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="15e54-112">Especifica el requisito para un encabezado de token de seguridad emitido (IssuedTokens de WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="15e54-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="15e54-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="15e54-113">TransactionProtocol</span></span>  
 <span data-ttu-id="15e54-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="15e54-114">Data type: string</span></span>  
  
 <span data-ttu-id="15e54-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="15e54-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="15e54-116">El protocolo de transacciones utilizado por el servicio para fluir las transacciones.</span><span class="sxs-lookup"><span data-stu-id="15e54-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="15e54-117">Transacciones</span><span class="sxs-lookup"><span data-stu-id="15e54-117">Transactions</span></span>  
 <span data-ttu-id="15e54-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="15e54-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="15e54-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="15e54-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="15e54-120">Indica si se admite la transacción entrante.</span><span class="sxs-lookup"><span data-stu-id="15e54-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15e54-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15e54-121">Requirements</span></span>  
  
|<span data-ttu-id="15e54-122">MOF</span><span class="sxs-lookup"><span data-stu-id="15e54-122">MOF</span></span>|<span data-ttu-id="15e54-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="15e54-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="15e54-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="15e54-124">Namespace</span></span>|<span data-ttu-id="15e54-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="15e54-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="15e54-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="15e54-126">See also</span></span>

- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
