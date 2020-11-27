---
title: Binding2
ms.date: 03/30/2017
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
ms.openlocfilehash: b72bd3903b7139c4adf2a8bd0ced6c34e7285640
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274301"
---
# <a name="binding"></a><span data-ttu-id="a999e-102">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a999e-102">Binding</span></span>

<span data-ttu-id="a999e-103">Enlace wmi</span><span class="sxs-lookup"><span data-stu-id="a999e-103">wmi Binding</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a999e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a999e-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="a999e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="a999e-105">Methods</span></span>  

 <span data-ttu-id="a999e-106">La clase Binding no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="a999e-106">The Binding class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a999e-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a999e-107">Properties</span></span>  

 <span data-ttu-id="a999e-108">La clase Binding tiene las propiedades siguientes.</span><span class="sxs-lookup"><span data-stu-id="a999e-108">The Binding class has the following properties.</span></span>  
  
### <a name="bindingelements"></a><span data-ttu-id="a999e-109">BindingElements</span><span class="sxs-lookup"><span data-stu-id="a999e-109">BindingElements</span></span>  

 <span data-ttu-id="a999e-110">Tipo de datos: matriz de BindingElement</span><span class="sxs-lookup"><span data-stu-id="a999e-110">Data type: BindingElement array</span></span>  
  
 <span data-ttu-id="a999e-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a999e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a999e-112">La colección de elementos de enlace implementada por el enlace.</span><span class="sxs-lookup"><span data-stu-id="a999e-112">The collection of binding elements implemented by the binding.</span></span>  
  
### <a name="closetimeout"></a><span data-ttu-id="a999e-113">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="a999e-113">CloseTimeout</span></span>  

 <span data-ttu-id="a999e-114">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="a999e-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="a999e-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a999e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a999e-116">El intervalo de tiempo proporcionado para que se complete una operación de cierre.</span><span class="sxs-lookup"><span data-stu-id="a999e-116">The interval of time provided for a close operation to complete.</span></span>  
  
### <a name="name"></a><span data-ttu-id="a999e-117">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="a999e-117">Name</span></span>  

 <span data-ttu-id="a999e-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="a999e-118">Data type: string</span></span>  
  
 <span data-ttu-id="a999e-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a999e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a999e-120">Nombre del enlace.</span><span class="sxs-lookup"><span data-stu-id="a999e-120">The name of the binding.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="a999e-121">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="a999e-121">Namespace</span></span>  

 <span data-ttu-id="a999e-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="a999e-122">Data type: string</span></span>  
  
 <span data-ttu-id="a999e-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a999e-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a999e-124">Espacio de nombres XML del enlace.</span><span class="sxs-lookup"><span data-stu-id="a999e-124">The XML namespace of the binding.</span></span>  
  
### <a name="opentimeout"></a><span data-ttu-id="a999e-125">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="a999e-125">OpenTimeout</span></span>  

 <span data-ttu-id="a999e-126">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="a999e-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="a999e-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a999e-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a999e-128">El intervalo de tiempo proporcionado para que se complete una operación de apertura.</span><span class="sxs-lookup"><span data-stu-id="a999e-128">The interval of time provided for an open operation to complete.</span></span>  
  
### <a name="receivetimeout"></a><span data-ttu-id="a999e-129">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="a999e-129">ReceiveTimeout</span></span>  

 <span data-ttu-id="a999e-130">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="a999e-130">Data type: datetime</span></span>  
  
 <span data-ttu-id="a999e-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a999e-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a999e-132">El intervalo de tiempo proporcionado para que se complete una operación de recepción.</span><span class="sxs-lookup"><span data-stu-id="a999e-132">The interval of time provided for a receive operation to complete.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="a999e-133">Scheme</span><span class="sxs-lookup"><span data-stu-id="a999e-133">Scheme</span></span>  

 <span data-ttu-id="a999e-134">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="a999e-134">Data type: string</span></span>  
  
 <span data-ttu-id="a999e-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a999e-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a999e-136">El esquema de transporte de URI utilizado por los generadores de canales y de agentes de escucha creados por el enlace.</span><span class="sxs-lookup"><span data-stu-id="a999e-136">The URI transport scheme that is used by the channel and listener factories that are built by the binding.</span></span>  
  
### <a name="sendtimeout"></a><span data-ttu-id="a999e-137">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="a999e-137">SendTimeout</span></span>  

 <span data-ttu-id="a999e-138">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="a999e-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="a999e-139">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a999e-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a999e-140">El intervalo de tiempo proporcionado para que se complete una operación de envío.</span><span class="sxs-lookup"><span data-stu-id="a999e-140">The interval of time provided for a send operation to complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a999e-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a999e-141">Requirements</span></span>  
  
|<span data-ttu-id="a999e-142">MOF</span><span class="sxs-lookup"><span data-stu-id="a999e-142">MOF</span></span>|<span data-ttu-id="a999e-143">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a999e-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a999e-144">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="a999e-144">Namespace</span></span>|<span data-ttu-id="a999e-145">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a999e-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a999e-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="a999e-146">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
