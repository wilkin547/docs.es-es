---
title: Clase de operación
ms.date: 03/30/2017
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
ms.openlocfilehash: 16de8b25594896349ea546d3def52dd256fe5c70
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180944"
---
# <a name="operation-class"></a><span data-ttu-id="406bb-102">Clase de operación</span><span class="sxs-lookup"><span data-stu-id="406bb-102">Operation class</span></span>
<span data-ttu-id="406bb-103">Operación</span><span class="sxs-lookup"><span data-stu-id="406bb-103">Operation</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="406bb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="406bb-104">Syntax</span></span>  
  
```csharp
class Operation  
{  
  string Action;  
  boolean AsyncPattern;  
  Behavior Behaviors[];  
  boolean IsCallback;  
  boolean IsInitiating;  
  boolean IsOneWay;  
  boolean IsTerminating;  
  string MethodSignature;  
  string Name;  
  string ParameterTypes[];  
  string ReplyAction;  
  string ReturnType;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="406bb-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="406bb-105">Methods</span></span>  
 <span data-ttu-id="406bb-106">La clase Operación no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="406bb-106">The Operation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="406bb-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="406bb-107">Properties</span></span>  
 <span data-ttu-id="406bb-108">La clase Operación tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="406bb-108">The Operation class has the following properties:</span></span>  
  
### <a name="action"></a><span data-ttu-id="406bb-109">Acción</span><span class="sxs-lookup"><span data-stu-id="406bb-109">Action</span></span>  
 <span data-ttu-id="406bb-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="406bb-110">Data type: string</span></span>  
  
 <span data-ttu-id="406bb-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="406bb-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="406bb-112">La acción WS-Addressing del mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="406bb-112">The WS-Addressing action of the request message.</span></span>  
  
### <a name="asyncpattern"></a><span data-ttu-id="406bb-113">AsyncPattern</span><span class="sxs-lookup"><span data-stu-id="406bb-113">AsyncPattern</span></span>  
 <span data-ttu-id="406bb-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="406bb-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="406bb-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="406bb-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="406bb-116">Indica que una operación se implementa de forma asincrónica utilizando un `Begin`[Abrir/cerrar corchetes angulares] y `End`[entre corchetes angulares de apertura y cierre] el par de métodos en un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="406bb-116">Indicates that an operation is implemented asynchronously using a `Begin`[open/close angle brackets] and `End`[open/close angle brackets] method pair in a service contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="406bb-117">comportamientos</span><span class="sxs-lookup"><span data-stu-id="406bb-117">Behaviors</span></span>  
 <span data-ttu-id="406bb-118">Tipo de datos: matriz de comportamientos</span><span class="sxs-lookup"><span data-stu-id="406bb-118">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="406bb-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="406bb-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="406bb-120">Los comportamientos asociados a esta operación.</span><span class="sxs-lookup"><span data-stu-id="406bb-120">The behaviors associated with this operation.</span></span>  
  
### <a name="iscallback"></a><span data-ttu-id="406bb-121">IsCallback</span><span class="sxs-lookup"><span data-stu-id="406bb-121">IsCallback</span></span>  
 <span data-ttu-id="406bb-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="406bb-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="406bb-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="406bb-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="406bb-124">Verdadero cuando la operación es una operación de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="406bb-124">True when the operation is a callback operation.</span></span>  
  
### <a name="isinitiating"></a><span data-ttu-id="406bb-125">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="406bb-125">IsInitiating</span></span>  
 <span data-ttu-id="406bb-126">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="406bb-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="406bb-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="406bb-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="406bb-128">Indica si el método implementa una operación que puede iniciar una sesión en el servidor.</span><span class="sxs-lookup"><span data-stu-id="406bb-128">Indicates whether the method implements an operation that can initiate a session on the server.</span></span>  
  
### <a name="isoneway"></a><span data-ttu-id="406bb-129">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="406bb-129">IsOneWay</span></span>  
 <span data-ttu-id="406bb-130">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="406bb-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="406bb-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="406bb-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="406bb-132">Indica si una operación devuelve un mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="406bb-132">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="isterminating"></a><span data-ttu-id="406bb-133">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="406bb-133">IsTerminating</span></span>  
 <span data-ttu-id="406bb-134">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="406bb-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="406bb-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="406bb-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="406bb-136">Indica si una operación devuelve un mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="406bb-136">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="methodsignature"></a><span data-ttu-id="406bb-137">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="406bb-137">MethodSignature</span></span>  
 <span data-ttu-id="406bb-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="406bb-138">Data type: string</span></span>  
  
 <span data-ttu-id="406bb-139">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="406bb-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="406bb-140">La firma del método de la operación.</span><span class="sxs-lookup"><span data-stu-id="406bb-140">The method signature of the operation.</span></span>  
  
### <a name="name"></a><span data-ttu-id="406bb-141">nombre</span><span class="sxs-lookup"><span data-stu-id="406bb-141">Name</span></span>  
 <span data-ttu-id="406bb-142">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="406bb-142">Data type: string</span></span>  
  
 <span data-ttu-id="406bb-143">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="406bb-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="406bb-144">Nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="406bb-144">The name of the operation.</span></span>  
  
### <a name="parametertypes"></a><span data-ttu-id="406bb-145">ParameterTypes</span><span class="sxs-lookup"><span data-stu-id="406bb-145">ParameterTypes</span></span>  
 <span data-ttu-id="406bb-146">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="406bb-146">Data type: string array</span></span>  
  
 <span data-ttu-id="406bb-147">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="406bb-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="406bb-148">Tipos de los parámetros de la operación.</span><span class="sxs-lookup"><span data-stu-id="406bb-148">The types of the parameters of the operation.</span></span>  
  
### <a name="replyaction"></a><span data-ttu-id="406bb-149">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="406bb-149">ReplyAction</span></span>  
 <span data-ttu-id="406bb-150">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="406bb-150">Data type: string</span></span>  
  
 <span data-ttu-id="406bb-151">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="406bb-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="406bb-152">El valor de la acción SOAP para el mensaje de respuesta de la operación.</span><span class="sxs-lookup"><span data-stu-id="406bb-152">The value of the SOAP action for the reply message of the operation.</span></span>  
  
### <a name="returntype"></a><span data-ttu-id="406bb-153">ReturnType</span><span class="sxs-lookup"><span data-stu-id="406bb-153">ReturnType</span></span>  
 <span data-ttu-id="406bb-154">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="406bb-154">Data type: string</span></span>  
  
 <span data-ttu-id="406bb-155">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="406bb-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="406bb-156">Tipo devuelto de la operación.</span><span class="sxs-lookup"><span data-stu-id="406bb-156">The return type of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="406bb-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="406bb-157">Requirements</span></span>  
  
|<span data-ttu-id="406bb-158">MOF</span><span class="sxs-lookup"><span data-stu-id="406bb-158">MOF</span></span>|<span data-ttu-id="406bb-159">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="406bb-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="406bb-160">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="406bb-160">Namespace</span></span>|<span data-ttu-id="406bb-161">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="406bb-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="406bb-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="406bb-162">See Also</span></span>  
 <xref:System.ServiceModel.Description.OperationDescription>
