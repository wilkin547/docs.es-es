---
title: Binding2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b9e44d161e1229db9145f4ed7e337396bbd98c68
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="binding"></a><span data-ttu-id="c63b1-102">Enlaces</span><span class="sxs-lookup"><span data-stu-id="c63b1-102">Binding</span></span>
<span data-ttu-id="c63b1-103">Enlace wmi</span><span class="sxs-lookup"><span data-stu-id="c63b1-103">wmi Binding</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c63b1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c63b1-104">Syntax</span></span>  
  
```  
class Binding  
{  
  BindingElement BindingElements[];  
  datetime CloseTimeout;  
  string Name;  
  string Namespace;  
  datetime OpenTimeout;  
  datetime ReceiveTimeout;  
  string Scheme;  
  datetime SendTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c63b1-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="c63b1-105">Methods</span></span>  
 <span data-ttu-id="c63b1-106">La clase Binding no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="c63b1-106">The Binding class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c63b1-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="c63b1-107">Properties</span></span>  
 <span data-ttu-id="c63b1-108">La clase Binding tiene las propiedades siguientes.</span><span class="sxs-lookup"><span data-stu-id="c63b1-108">The Binding class has the following properties.</span></span>  
  
### <a name="bindingelements"></a><span data-ttu-id="c63b1-109">BindingElements</span><span class="sxs-lookup"><span data-stu-id="c63b1-109">BindingElements</span></span>  
 <span data-ttu-id="c63b1-110">Tipo de datos: matriz de BindingElement</span><span class="sxs-lookup"><span data-stu-id="c63b1-110">Data type: BindingElement array</span></span>  
  
 <span data-ttu-id="c63b1-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c63b1-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c63b1-112">La colección de elementos de enlace implementada por el enlace.</span><span class="sxs-lookup"><span data-stu-id="c63b1-112">The collection of binding elements implemented by the binding.</span></span>  
  
### <a name="closetimeout"></a><span data-ttu-id="c63b1-113">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="c63b1-113">CloseTimeout</span></span>  
 <span data-ttu-id="c63b1-114">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="c63b1-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="c63b1-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c63b1-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c63b1-116">El intervalo de tiempo proporcionado para que se complete una operación de cierre.</span><span class="sxs-lookup"><span data-stu-id="c63b1-116">The interval of time provided for a close operation to complete.</span></span>  
  
### <a name="name"></a><span data-ttu-id="c63b1-117">Nombre</span><span class="sxs-lookup"><span data-stu-id="c63b1-117">Name</span></span>  
 <span data-ttu-id="c63b1-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="c63b1-118">Data type: string</span></span>  
  
 <span data-ttu-id="c63b1-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c63b1-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c63b1-120">Nombre del enlace.</span><span class="sxs-lookup"><span data-stu-id="c63b1-120">The name of the binding.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="c63b1-121">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="c63b1-121">Namespace</span></span>  
 <span data-ttu-id="c63b1-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="c63b1-122">Data type: string</span></span>  
  
 <span data-ttu-id="c63b1-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c63b1-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c63b1-124">Espacio de nombres XML del enlace.</span><span class="sxs-lookup"><span data-stu-id="c63b1-124">The XML namespace of the binding.</span></span>  
  
### <a name="opentimeout"></a><span data-ttu-id="c63b1-125">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="c63b1-125">OpenTimeout</span></span>  
 <span data-ttu-id="c63b1-126">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="c63b1-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="c63b1-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c63b1-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c63b1-128">El intervalo de tiempo proporcionado para que se complete una operación de apertura.</span><span class="sxs-lookup"><span data-stu-id="c63b1-128">The interval of time provided for an open operation to complete.</span></span>  
  
### <a name="receivetimeout"></a><span data-ttu-id="c63b1-129">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="c63b1-129">ReceiveTimeout</span></span>  
 <span data-ttu-id="c63b1-130">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="c63b1-130">Data type: datetime</span></span>  
  
 <span data-ttu-id="c63b1-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c63b1-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c63b1-132">El intervalo de tiempo proporcionado para que se complete una operación de recepción.</span><span class="sxs-lookup"><span data-stu-id="c63b1-132">The interval of time provided for a receive operation to complete.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="c63b1-133">Scheme</span><span class="sxs-lookup"><span data-stu-id="c63b1-133">Scheme</span></span>  
 <span data-ttu-id="c63b1-134">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="c63b1-134">Data type: string</span></span>  
  
 <span data-ttu-id="c63b1-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c63b1-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c63b1-136">El esquema de transporte de URI utilizado por los generadores de canales y de agentes de escucha creados por el enlace.</span><span class="sxs-lookup"><span data-stu-id="c63b1-136">The URI transport scheme that is used by the channel and listener factories that are built by the binding.</span></span>  
  
### <a name="sendtimeout"></a><span data-ttu-id="c63b1-137">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="c63b1-137">SendTimeout</span></span>  
 <span data-ttu-id="c63b1-138">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="c63b1-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="c63b1-139">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c63b1-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c63b1-140">El intervalo de tiempo proporcionado para que se complete una operación de envío.</span><span class="sxs-lookup"><span data-stu-id="c63b1-140">The interval of time provided for a send operation to complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c63b1-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c63b1-141">Requirements</span></span>  
  
|<span data-ttu-id="c63b1-142">MOF</span><span class="sxs-lookup"><span data-stu-id="c63b1-142">MOF</span></span>|<span data-ttu-id="c63b1-143">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c63b1-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c63b1-144">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="c63b1-144">Namespace</span></span>|<span data-ttu-id="c63b1-145">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c63b1-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c63b1-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="c63b1-146">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>
