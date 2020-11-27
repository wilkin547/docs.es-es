---
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: 76cc619aed4ba2b944a8d11dc454a40368a4068c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269085"
---
# <a name="operationbehaviorattribute"></a><span data-ttu-id="72438-102">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="72438-102">OperationBehaviorAttribute</span></span>

<span data-ttu-id="72438-103">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="72438-103">OperationBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72438-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="72438-104">Syntax</span></span>  
  
```csharp
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="72438-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="72438-105">Methods</span></span>  

 <span data-ttu-id="72438-106">La clase OperationBehaviorAttribute no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="72438-106">The OperationBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="72438-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="72438-107">Properties</span></span>  

 <span data-ttu-id="72438-108">La clase OperationBehaviorAttribute tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="72438-108">The OperationBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="autodisposeparameters"></a><span data-ttu-id="72438-109">AutoDisposeParameters</span><span class="sxs-lookup"><span data-stu-id="72438-109">AutoDisposeParameters</span></span>  

 <span data-ttu-id="72438-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="72438-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="72438-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="72438-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="72438-112">El estado de la característica de eliminación automática para parámetros.</span><span class="sxs-lookup"><span data-stu-id="72438-112">The state of the auto-dispose feature for parameters.</span></span>  
  
### <a name="impersonation"></a><span data-ttu-id="72438-113">Suplantación</span><span class="sxs-lookup"><span data-stu-id="72438-113">Impersonation</span></span>  

 <span data-ttu-id="72438-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="72438-114">Data type: string</span></span>  
  
 <span data-ttu-id="72438-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="72438-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="72438-116">Indica el nivel de suplantación del llamador que la operación admite.</span><span class="sxs-lookup"><span data-stu-id="72438-116">Indicates the level of caller impersonation that the operation supports.</span></span>  
  
### <a name="releaseinstancemode"></a><span data-ttu-id="72438-117">ReleaseInstanceMode</span><span class="sxs-lookup"><span data-stu-id="72438-117">ReleaseInstanceMode</span></span>  

 <span data-ttu-id="72438-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="72438-118">Data type: string</span></span>  
  
 <span data-ttu-id="72438-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="72438-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="72438-120">Indica cuándo durante el curso de una invocación de la operación debe reciclarse el objeto.</span><span class="sxs-lookup"><span data-stu-id="72438-120">Indicates when in the course of an operation invocation to recycle the object.</span></span>  
  
### <a name="transactionautocomplete"></a><span data-ttu-id="72438-121">TransactionAutoComplete</span><span class="sxs-lookup"><span data-stu-id="72438-121">TransactionAutoComplete</span></span>  

 <span data-ttu-id="72438-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="72438-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="72438-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="72438-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="72438-124">Indica si confirmar automáticamente la transacción actual si no se produce ninguna excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="72438-124">Indicates whether to automatically commit the current transaction if no unhandled exceptions occur.</span></span>  
  
### <a name="transactionscoperequired"></a><span data-ttu-id="72438-125">TransactionScopeRequired</span><span class="sxs-lookup"><span data-stu-id="72438-125">TransactionScopeRequired</span></span>  

 <span data-ttu-id="72438-126">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="72438-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="72438-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="72438-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="72438-128">Indica si la operación requiere una transacción.</span><span class="sxs-lookup"><span data-stu-id="72438-128">Indicates whether the operation requires a transaction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72438-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="72438-129">Requirements</span></span>  
  
|<span data-ttu-id="72438-130">MOF</span><span class="sxs-lookup"><span data-stu-id="72438-130">MOF</span></span>|<span data-ttu-id="72438-131">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="72438-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="72438-132">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="72438-132">Namespace</span></span>|<span data-ttu-id="72438-133">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="72438-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="72438-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="72438-134">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
