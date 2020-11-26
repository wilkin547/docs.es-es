---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: 577502d1cd3d81784cb9b1eb3b249376b8ffa6b8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234900"
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="8dece-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="8dece-102">TransactionFlowBindingElement</span></span>

<span data-ttu-id="8dece-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="8dece-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dece-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8dece-104">Syntax</span></span>  
  
```csharp
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8dece-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="8dece-105">Methods</span></span>  

 <span data-ttu-id="8dece-106">La clase TransactionFlowBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="8dece-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8dece-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="8dece-107">Properties</span></span>  

 <span data-ttu-id="8dece-108">La clase TransactionFlowBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="8dece-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="8dece-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="8dece-109">IssuedTokens</span></span>  

 <span data-ttu-id="8dece-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="8dece-110">Data type: string</span></span>  
  
 <span data-ttu-id="8dece-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="8dece-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8dece-112">Especifica el requisito para un encabezado de token de seguridad emitido (IssuedTokens de WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="8dece-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="8dece-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="8dece-113">TransactionProtocol</span></span>  

 <span data-ttu-id="8dece-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="8dece-114">Data type: string</span></span>  
  
 <span data-ttu-id="8dece-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="8dece-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8dece-116">El protocolo de transacciones utilizado por el servicio para fluir las transacciones.</span><span class="sxs-lookup"><span data-stu-id="8dece-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="8dece-117">Transacciones</span><span class="sxs-lookup"><span data-stu-id="8dece-117">Transactions</span></span>  

 <span data-ttu-id="8dece-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="8dece-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="8dece-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="8dece-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8dece-120">Indica si se admite la transacción entrante.</span><span class="sxs-lookup"><span data-stu-id="8dece-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8dece-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8dece-121">Requirements</span></span>  
  
|<span data-ttu-id="8dece-122">MOF</span><span class="sxs-lookup"><span data-stu-id="8dece-122">MOF</span></span>|<span data-ttu-id="8dece-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="8dece-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8dece-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="8dece-124">Namespace</span></span>|<span data-ttu-id="8dece-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8dece-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8dece-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="8dece-126">See also</span></span>

- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
