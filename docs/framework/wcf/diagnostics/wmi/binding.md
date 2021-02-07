---
description: 'Más información acerca de: enlace'
title: Binding2
ms.date: 03/30/2017
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
ms.openlocfilehash: 36887a9296bfafd0790105e7f4d513efc3009bf8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757792"
---
# <a name="binding"></a><span data-ttu-id="b7829-103">Enlace</span><span class="sxs-lookup"><span data-stu-id="b7829-103">Binding</span></span>

<span data-ttu-id="b7829-104">Enlace wmi</span><span class="sxs-lookup"><span data-stu-id="b7829-104">wmi Binding</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7829-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7829-105">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="b7829-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="b7829-106">Methods</span></span>  

 <span data-ttu-id="b7829-107">La clase Binding no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="b7829-107">The Binding class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b7829-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b7829-108">Properties</span></span>  

 <span data-ttu-id="b7829-109">La clase Binding tiene las propiedades siguientes.</span><span class="sxs-lookup"><span data-stu-id="b7829-109">The Binding class has the following properties.</span></span>  
  
### <a name="bindingelements"></a><span data-ttu-id="b7829-110">BindingElements</span><span class="sxs-lookup"><span data-stu-id="b7829-110">BindingElements</span></span>  

 <span data-ttu-id="b7829-111">Tipo de datos: matriz de BindingElement</span><span class="sxs-lookup"><span data-stu-id="b7829-111">Data type: BindingElement array</span></span>  
  
 <span data-ttu-id="b7829-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b7829-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b7829-113">La colección de elementos de enlace implementada por el enlace.</span><span class="sxs-lookup"><span data-stu-id="b7829-113">The collection of binding elements implemented by the binding.</span></span>  
  
### <a name="closetimeout"></a><span data-ttu-id="b7829-114">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="b7829-114">CloseTimeout</span></span>  

 <span data-ttu-id="b7829-115">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="b7829-115">Data type: datetime</span></span>  
  
 <span data-ttu-id="b7829-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b7829-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b7829-117">El intervalo de tiempo proporcionado para que se complete una operación de cierre.</span><span class="sxs-lookup"><span data-stu-id="b7829-117">The interval of time provided for a close operation to complete.</span></span>  
  
### <a name="name"></a><span data-ttu-id="b7829-118">Nombre</span><span class="sxs-lookup"><span data-stu-id="b7829-118">Name</span></span>  

 <span data-ttu-id="b7829-119">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b7829-119">Data type: string</span></span>  
  
 <span data-ttu-id="b7829-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b7829-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b7829-121">Nombre del enlace.</span><span class="sxs-lookup"><span data-stu-id="b7829-121">The name of the binding.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="b7829-122">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="b7829-122">Namespace</span></span>  

 <span data-ttu-id="b7829-123">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b7829-123">Data type: string</span></span>  
  
 <span data-ttu-id="b7829-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b7829-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b7829-125">Espacio de nombres XML del enlace.</span><span class="sxs-lookup"><span data-stu-id="b7829-125">The XML namespace of the binding.</span></span>  
  
### <a name="opentimeout"></a><span data-ttu-id="b7829-126">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="b7829-126">OpenTimeout</span></span>  

 <span data-ttu-id="b7829-127">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="b7829-127">Data type: datetime</span></span>  
  
 <span data-ttu-id="b7829-128">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b7829-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b7829-129">El intervalo de tiempo proporcionado para que se complete una operación de apertura.</span><span class="sxs-lookup"><span data-stu-id="b7829-129">The interval of time provided for an open operation to complete.</span></span>  
  
### <a name="receivetimeout"></a><span data-ttu-id="b7829-130">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="b7829-130">ReceiveTimeout</span></span>  

 <span data-ttu-id="b7829-131">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="b7829-131">Data type: datetime</span></span>  
  
 <span data-ttu-id="b7829-132">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b7829-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b7829-133">El intervalo de tiempo proporcionado para que se complete una operación de recepción.</span><span class="sxs-lookup"><span data-stu-id="b7829-133">The interval of time provided for a receive operation to complete.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="b7829-134">Scheme</span><span class="sxs-lookup"><span data-stu-id="b7829-134">Scheme</span></span>  

 <span data-ttu-id="b7829-135">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b7829-135">Data type: string</span></span>  
  
 <span data-ttu-id="b7829-136">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b7829-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b7829-137">El esquema de transporte de URI utilizado por los generadores de canales y de agentes de escucha creados por el enlace.</span><span class="sxs-lookup"><span data-stu-id="b7829-137">The URI transport scheme that is used by the channel and listener factories that are built by the binding.</span></span>  
  
### <a name="sendtimeout"></a><span data-ttu-id="b7829-138">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="b7829-138">SendTimeout</span></span>  

 <span data-ttu-id="b7829-139">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="b7829-139">Data type: datetime</span></span>  
  
 <span data-ttu-id="b7829-140">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b7829-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b7829-141">El intervalo de tiempo proporcionado para que se complete una operación de envío.</span><span class="sxs-lookup"><span data-stu-id="b7829-141">The interval of time provided for a send operation to complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7829-142">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7829-142">Requirements</span></span>  
  
|<span data-ttu-id="b7829-143">MOF</span><span class="sxs-lookup"><span data-stu-id="b7829-143">MOF</span></span>|<span data-ttu-id="b7829-144">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b7829-144">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b7829-145">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="b7829-145">Namespace</span></span>|<span data-ttu-id="b7829-146">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b7829-146">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b7829-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7829-147">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
