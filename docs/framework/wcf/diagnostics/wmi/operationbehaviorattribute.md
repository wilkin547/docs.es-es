---
description: 'Más información acerca de: OperationBehaviorAttribute'
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: c1f1b80134163ee65d5015e52017f5bb455aeac7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803066"
---
# <a name="operationbehaviorattribute"></a><span data-ttu-id="6b9c1-103">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="6b9c1-103">OperationBehaviorAttribute</span></span>

<span data-ttu-id="6b9c1-104">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="6b9c1-104">OperationBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b9c1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b9c1-105">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="6b9c1-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="6b9c1-106">Methods</span></span>  

 <span data-ttu-id="6b9c1-107">La clase OperationBehaviorAttribute no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="6b9c1-107">The OperationBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6b9c1-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="6b9c1-108">Properties</span></span>  

 <span data-ttu-id="6b9c1-109">La clase OperationBehaviorAttribute tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="6b9c1-109">The OperationBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="autodisposeparameters"></a><span data-ttu-id="6b9c1-110">AutoDisposeParameters</span><span class="sxs-lookup"><span data-stu-id="6b9c1-110">AutoDisposeParameters</span></span>  

 <span data-ttu-id="6b9c1-111">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="6b9c1-111">Data type: boolean</span></span>  
  
 <span data-ttu-id="6b9c1-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6b9c1-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6b9c1-113">El estado de la característica de eliminación automática para parámetros.</span><span class="sxs-lookup"><span data-stu-id="6b9c1-113">The state of the auto-dispose feature for parameters.</span></span>  
  
### <a name="impersonation"></a><span data-ttu-id="6b9c1-114">Suplantación</span><span class="sxs-lookup"><span data-stu-id="6b9c1-114">Impersonation</span></span>  

 <span data-ttu-id="6b9c1-115">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="6b9c1-115">Data type: string</span></span>  
  
 <span data-ttu-id="6b9c1-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6b9c1-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6b9c1-117">Indica el nivel de suplantación del llamador que la operación admite.</span><span class="sxs-lookup"><span data-stu-id="6b9c1-117">Indicates the level of caller impersonation that the operation supports.</span></span>  
  
### <a name="releaseinstancemode"></a><span data-ttu-id="6b9c1-118">ReleaseInstanceMode</span><span class="sxs-lookup"><span data-stu-id="6b9c1-118">ReleaseInstanceMode</span></span>  

 <span data-ttu-id="6b9c1-119">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="6b9c1-119">Data type: string</span></span>  
  
 <span data-ttu-id="6b9c1-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6b9c1-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6b9c1-121">Indica cuándo durante el curso de una invocación de la operación debe reciclarse el objeto.</span><span class="sxs-lookup"><span data-stu-id="6b9c1-121">Indicates when in the course of an operation invocation to recycle the object.</span></span>  
  
### <a name="transactionautocomplete"></a><span data-ttu-id="6b9c1-122">TransactionAutoComplete</span><span class="sxs-lookup"><span data-stu-id="6b9c1-122">TransactionAutoComplete</span></span>  

 <span data-ttu-id="6b9c1-123">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="6b9c1-123">Data type: boolean</span></span>  
  
 <span data-ttu-id="6b9c1-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6b9c1-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6b9c1-125">Indica si confirmar automáticamente la transacción actual si no se produce ninguna excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="6b9c1-125">Indicates whether to automatically commit the current transaction if no unhandled exceptions occur.</span></span>  
  
### <a name="transactionscoperequired"></a><span data-ttu-id="6b9c1-126">TransactionScopeRequired</span><span class="sxs-lookup"><span data-stu-id="6b9c1-126">TransactionScopeRequired</span></span>  

 <span data-ttu-id="6b9c1-127">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="6b9c1-127">Data type: boolean</span></span>  
  
 <span data-ttu-id="6b9c1-128">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6b9c1-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6b9c1-129">Indica si la operación requiere una transacción.</span><span class="sxs-lookup"><span data-stu-id="6b9c1-129">Indicates whether the operation requires a transaction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b9c1-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6b9c1-130">Requirements</span></span>  
  
|<span data-ttu-id="6b9c1-131">MOF</span><span class="sxs-lookup"><span data-stu-id="6b9c1-131">MOF</span></span>|<span data-ttu-id="6b9c1-132">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6b9c1-132">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6b9c1-133">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="6b9c1-133">Namespace</span></span>|<span data-ttu-id="6b9c1-134">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6b9c1-134">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6b9c1-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b9c1-135">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
