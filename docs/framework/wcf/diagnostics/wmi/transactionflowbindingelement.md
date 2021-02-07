---
description: 'Más información acerca de: TransactionFlowBindingElement'
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: 6a96a83c563affdaef01a12d64bc1c13ab2f719e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757142"
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="62a14-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="62a14-103">TransactionFlowBindingElement</span></span>

<span data-ttu-id="62a14-104">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="62a14-104">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62a14-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62a14-105">Syntax</span></span>  
  
```csharp
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="62a14-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="62a14-106">Methods</span></span>  

 <span data-ttu-id="62a14-107">La clase TransactionFlowBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="62a14-107">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="62a14-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="62a14-108">Properties</span></span>  

 <span data-ttu-id="62a14-109">La clase TransactionFlowBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="62a14-109">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="62a14-110">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="62a14-110">IssuedTokens</span></span>  

 <span data-ttu-id="62a14-111">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="62a14-111">Data type: string</span></span>  
  
 <span data-ttu-id="62a14-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="62a14-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62a14-113">Especifica el requisito para un encabezado de token de seguridad emitido (IssuedTokens de WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="62a14-113">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="62a14-114">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="62a14-114">TransactionProtocol</span></span>  

 <span data-ttu-id="62a14-115">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="62a14-115">Data type: string</span></span>  
  
 <span data-ttu-id="62a14-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="62a14-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62a14-117">El protocolo de transacciones utilizado por el servicio para fluir las transacciones.</span><span class="sxs-lookup"><span data-stu-id="62a14-117">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="62a14-118">Transacciones</span><span class="sxs-lookup"><span data-stu-id="62a14-118">Transactions</span></span>  

 <span data-ttu-id="62a14-119">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="62a14-119">Data type: boolean</span></span>  
  
 <span data-ttu-id="62a14-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="62a14-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62a14-121">Indica si se admite la transacción entrante.</span><span class="sxs-lookup"><span data-stu-id="62a14-121">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62a14-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62a14-122">Requirements</span></span>  
  
|<span data-ttu-id="62a14-123">MOF</span><span class="sxs-lookup"><span data-stu-id="62a14-123">MOF</span></span>|<span data-ttu-id="62a14-124">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="62a14-124">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="62a14-125">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="62a14-125">Namespace</span></span>|<span data-ttu-id="62a14-126">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="62a14-126">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62a14-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="62a14-127">See also</span></span>

- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
