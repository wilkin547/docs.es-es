---
title: OperationBehaviorAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fd01c5c4d37f5c0ec5673dc9aa4a47cb8affbc29
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="operationbehaviorattribute"></a><span data-ttu-id="47fdb-102">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="47fdb-102">OperationBehaviorAttribute</span></span>
<span data-ttu-id="47fdb-103">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="47fdb-103">OperationBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47fdb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47fdb-104">Syntax</span></span>  
  
```  
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="47fdb-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="47fdb-105">Methods</span></span>  
 <span data-ttu-id="47fdb-106">La clase OperationBehaviorAttribute no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="47fdb-106">The OperationBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="47fdb-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="47fdb-107">Properties</span></span>  
 <span data-ttu-id="47fdb-108">La clase OperationBehaviorAttribute tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="47fdb-108">The OperationBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="autodisposeparameters"></a><span data-ttu-id="47fdb-109">AutoDisposeParameters</span><span class="sxs-lookup"><span data-stu-id="47fdb-109">AutoDisposeParameters</span></span>  
 <span data-ttu-id="47fdb-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="47fdb-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="47fdb-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="47fdb-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="47fdb-112">El estado de la característica de eliminación automática para parámetros.</span><span class="sxs-lookup"><span data-stu-id="47fdb-112">The state of the auto-dispose feature for parameters.</span></span>  
  
### <a name="impersonation"></a><span data-ttu-id="47fdb-113">Suplantación</span><span class="sxs-lookup"><span data-stu-id="47fdb-113">Impersonation</span></span>  
 <span data-ttu-id="47fdb-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="47fdb-114">Data type: string</span></span>  
  
 <span data-ttu-id="47fdb-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="47fdb-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="47fdb-116">Indica el nivel de suplantación del llamador que la operación admite.</span><span class="sxs-lookup"><span data-stu-id="47fdb-116">Indicates the level of caller impersonation that the operation supports.</span></span>  
  
### <a name="releaseinstancemode"></a><span data-ttu-id="47fdb-117">ReleaseInstanceMode</span><span class="sxs-lookup"><span data-stu-id="47fdb-117">ReleaseInstanceMode</span></span>  
 <span data-ttu-id="47fdb-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="47fdb-118">Data type: string</span></span>  
  
 <span data-ttu-id="47fdb-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="47fdb-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="47fdb-120">Indica cuándo durante el curso de una invocación de la operación debe reciclarse el objeto.</span><span class="sxs-lookup"><span data-stu-id="47fdb-120">Indicates when in the course of an operation invocation to recycle the object.</span></span>  
  
### <a name="transactionautocomplete"></a><span data-ttu-id="47fdb-121">TransactionAutoComplete</span><span class="sxs-lookup"><span data-stu-id="47fdb-121">TransactionAutoComplete</span></span>  
 <span data-ttu-id="47fdb-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="47fdb-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="47fdb-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="47fdb-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="47fdb-124">Indica si confirmar automáticamente la transacción actual si no se produce ninguna excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="47fdb-124">Indicates whether to automatically commit the current transaction if no unhandled exceptions occur.</span></span>  
  
### <a name="transactionscoperequired"></a><span data-ttu-id="47fdb-125">TransactionScopeRequired</span><span class="sxs-lookup"><span data-stu-id="47fdb-125">TransactionScopeRequired</span></span>  
 <span data-ttu-id="47fdb-126">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="47fdb-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="47fdb-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="47fdb-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="47fdb-128">Indica si la operación requiere una transacción.</span><span class="sxs-lookup"><span data-stu-id="47fdb-128">Indicates whether the operation requires a transaction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47fdb-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47fdb-129">Requirements</span></span>  
  
|<span data-ttu-id="47fdb-130">MOF</span><span class="sxs-lookup"><span data-stu-id="47fdb-130">MOF</span></span>|<span data-ttu-id="47fdb-131">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="47fdb-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="47fdb-132">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="47fdb-132">Namespace</span></span>|<span data-ttu-id="47fdb-133">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="47fdb-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="47fdb-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="47fdb-134">See Also</span></span>  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
