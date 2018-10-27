---
title: Binding2
ms.date: 03/30/2017
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
ms.openlocfilehash: 84e304f3dedcbd785d6238e6cb5eb142c288b995
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50033838"
---
# <a name="binding"></a><span data-ttu-id="e5770-102">Enlaces</span><span class="sxs-lookup"><span data-stu-id="e5770-102">Binding</span></span>
<span data-ttu-id="e5770-103">Enlace wmi</span><span class="sxs-lookup"><span data-stu-id="e5770-103">wmi Binding</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5770-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5770-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="e5770-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="e5770-105">Methods</span></span>  
 <span data-ttu-id="e5770-106">La clase Binding no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="e5770-106">The Binding class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e5770-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e5770-107">Properties</span></span>  
 <span data-ttu-id="e5770-108">La clase Binding tiene las propiedades siguientes.</span><span class="sxs-lookup"><span data-stu-id="e5770-108">The Binding class has the following properties.</span></span>  
  
### <a name="bindingelements"></a><span data-ttu-id="e5770-109">BindingElements</span><span class="sxs-lookup"><span data-stu-id="e5770-109">BindingElements</span></span>  
 <span data-ttu-id="e5770-110">Tipo de datos: matriz de BindingElement</span><span class="sxs-lookup"><span data-stu-id="e5770-110">Data type: BindingElement array</span></span>  
  
 <span data-ttu-id="e5770-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e5770-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5770-112">La colección de elementos de enlace implementada por el enlace.</span><span class="sxs-lookup"><span data-stu-id="e5770-112">The collection of binding elements implemented by the binding.</span></span>  
  
### <a name="closetimeout"></a><span data-ttu-id="e5770-113">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="e5770-113">CloseTimeout</span></span>  
 <span data-ttu-id="e5770-114">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="e5770-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="e5770-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e5770-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5770-116">El intervalo de tiempo proporcionado para que se complete una operación de cierre.</span><span class="sxs-lookup"><span data-stu-id="e5770-116">The interval of time provided for a close operation to complete.</span></span>  
  
### <a name="name"></a><span data-ttu-id="e5770-117">nombre</span><span class="sxs-lookup"><span data-stu-id="e5770-117">Name</span></span>  
 <span data-ttu-id="e5770-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e5770-118">Data type: string</span></span>  
  
 <span data-ttu-id="e5770-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e5770-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5770-120">Nombre del enlace.</span><span class="sxs-lookup"><span data-stu-id="e5770-120">The name of the binding.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="e5770-121">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="e5770-121">Namespace</span></span>  
 <span data-ttu-id="e5770-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e5770-122">Data type: string</span></span>  
  
 <span data-ttu-id="e5770-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e5770-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5770-124">Espacio de nombres XML del enlace.</span><span class="sxs-lookup"><span data-stu-id="e5770-124">The XML namespace of the binding.</span></span>  
  
### <a name="opentimeout"></a><span data-ttu-id="e5770-125">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="e5770-125">OpenTimeout</span></span>  
 <span data-ttu-id="e5770-126">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="e5770-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="e5770-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e5770-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5770-128">El intervalo de tiempo proporcionado para que se complete una operación de apertura.</span><span class="sxs-lookup"><span data-stu-id="e5770-128">The interval of time provided for an open operation to complete.</span></span>  
  
### <a name="receivetimeout"></a><span data-ttu-id="e5770-129">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="e5770-129">ReceiveTimeout</span></span>  
 <span data-ttu-id="e5770-130">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="e5770-130">Data type: datetime</span></span>  
  
 <span data-ttu-id="e5770-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e5770-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5770-132">El intervalo de tiempo proporcionado para que se complete una operación de recepción.</span><span class="sxs-lookup"><span data-stu-id="e5770-132">The interval of time provided for a receive operation to complete.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="e5770-133">Scheme</span><span class="sxs-lookup"><span data-stu-id="e5770-133">Scheme</span></span>  
 <span data-ttu-id="e5770-134">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e5770-134">Data type: string</span></span>  
  
 <span data-ttu-id="e5770-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e5770-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5770-136">El esquema de transporte de URI utilizado por los generadores de canales y de agentes de escucha creados por el enlace.</span><span class="sxs-lookup"><span data-stu-id="e5770-136">The URI transport scheme that is used by the channel and listener factories that are built by the binding.</span></span>  
  
### <a name="sendtimeout"></a><span data-ttu-id="e5770-137">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="e5770-137">SendTimeout</span></span>  
 <span data-ttu-id="e5770-138">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="e5770-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="e5770-139">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e5770-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5770-140">El intervalo de tiempo proporcionado para que se complete una operación de envío.</span><span class="sxs-lookup"><span data-stu-id="e5770-140">The interval of time provided for a send operation to complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5770-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5770-141">Requirements</span></span>  
  
|<span data-ttu-id="e5770-142">MOF</span><span class="sxs-lookup"><span data-stu-id="e5770-142">MOF</span></span>|<span data-ttu-id="e5770-143">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e5770-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e5770-144">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="e5770-144">Namespace</span></span>|<span data-ttu-id="e5770-145">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e5770-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5770-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5770-146">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>
