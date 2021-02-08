---
description: 'Más información sobre: clase de operación'
title: Operation class
ms.date: 03/30/2017
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
ms.openlocfilehash: 035c02bc05b7a64c5d15538001dbdcf2ec0b135b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803079"
---
# <a name="operation-class"></a><span data-ttu-id="f7428-103">Operation class</span><span class="sxs-lookup"><span data-stu-id="f7428-103">Operation class</span></span>

<span data-ttu-id="f7428-104">Operación</span><span class="sxs-lookup"><span data-stu-id="f7428-104">Operation</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7428-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7428-105">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="f7428-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="f7428-106">Methods</span></span>  

 <span data-ttu-id="f7428-107">La clase Operación no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="f7428-107">The Operation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f7428-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f7428-108">Properties</span></span>  

 <span data-ttu-id="f7428-109">La clase Operación tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="f7428-109">The Operation class has the following properties:</span></span>  
  
### <a name="action"></a><span data-ttu-id="f7428-110">Acción</span><span class="sxs-lookup"><span data-stu-id="f7428-110">Action</span></span>  

 <span data-ttu-id="f7428-111">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="f7428-111">Data type: string</span></span>  
  
 <span data-ttu-id="f7428-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f7428-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f7428-113">La acción WS-Addressing del mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="f7428-113">The WS-Addressing action of the request message.</span></span>  
  
### <a name="asyncpattern"></a><span data-ttu-id="f7428-114">AsyncPattern</span><span class="sxs-lookup"><span data-stu-id="f7428-114">AsyncPattern</span></span>  

 <span data-ttu-id="f7428-115">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="f7428-115">Data type: boolean</span></span>  
  
 <span data-ttu-id="f7428-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f7428-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f7428-117">Indica que una operación se implementa de forma asincrónica mediante un `Begin` par de métodos [abrir/cerrar corchetes angulares] y `End` [abrir/cerrar corchetes angulares] en un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="f7428-117">Indicates that an operation is implemented asynchronously using a `Begin`[open/close angle brackets] and `End`[open/close angle brackets] method pair in a service contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="f7428-118">Comportamientos</span><span class="sxs-lookup"><span data-stu-id="f7428-118">Behaviors</span></span>  

 <span data-ttu-id="f7428-119">Tipo de datos: matriz de comportamientos</span><span class="sxs-lookup"><span data-stu-id="f7428-119">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="f7428-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f7428-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f7428-121">Los comportamientos asociados a esta operación.</span><span class="sxs-lookup"><span data-stu-id="f7428-121">The behaviors associated with this operation.</span></span>  
  
### <a name="iscallback"></a><span data-ttu-id="f7428-122">IsCallback</span><span class="sxs-lookup"><span data-stu-id="f7428-122">IsCallback</span></span>  

 <span data-ttu-id="f7428-123">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="f7428-123">Data type: boolean</span></span>  
  
 <span data-ttu-id="f7428-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f7428-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f7428-125">Verdadero cuando la operación es una operación de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="f7428-125">True when the operation is a callback operation.</span></span>  
  
### <a name="isinitiating"></a><span data-ttu-id="f7428-126">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="f7428-126">IsInitiating</span></span>  

 <span data-ttu-id="f7428-127">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="f7428-127">Data type: boolean</span></span>  
  
 <span data-ttu-id="f7428-128">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f7428-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f7428-129">Indica si el método implementa una operación que puede iniciar una sesión en el servidor.</span><span class="sxs-lookup"><span data-stu-id="f7428-129">Indicates whether the method implements an operation that can initiate a session on the server.</span></span>  
  
### <a name="isoneway"></a><span data-ttu-id="f7428-130">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="f7428-130">IsOneWay</span></span>  

 <span data-ttu-id="f7428-131">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="f7428-131">Data type: boolean</span></span>  
  
 <span data-ttu-id="f7428-132">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f7428-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f7428-133">Indica si una operación devuelve un mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="f7428-133">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="isterminating"></a><span data-ttu-id="f7428-134">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="f7428-134">IsTerminating</span></span>  

 <span data-ttu-id="f7428-135">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="f7428-135">Data type: boolean</span></span>  
  
 <span data-ttu-id="f7428-136">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f7428-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f7428-137">Indica si una operación devuelve un mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="f7428-137">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="methodsignature"></a><span data-ttu-id="f7428-138">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="f7428-138">MethodSignature</span></span>  

 <span data-ttu-id="f7428-139">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="f7428-139">Data type: string</span></span>  
  
 <span data-ttu-id="f7428-140">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f7428-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f7428-141">La firma del método de la operación.</span><span class="sxs-lookup"><span data-stu-id="f7428-141">The method signature of the operation.</span></span>  
  
### <a name="name"></a><span data-ttu-id="f7428-142">Nombre</span><span class="sxs-lookup"><span data-stu-id="f7428-142">Name</span></span>  

 <span data-ttu-id="f7428-143">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="f7428-143">Data type: string</span></span>  
  
 <span data-ttu-id="f7428-144">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f7428-144">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f7428-145">Nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="f7428-145">The name of the operation.</span></span>  
  
### <a name="parametertypes"></a><span data-ttu-id="f7428-146">ParameterTypes</span><span class="sxs-lookup"><span data-stu-id="f7428-146">ParameterTypes</span></span>  

 <span data-ttu-id="f7428-147">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="f7428-147">Data type: string array</span></span>  
  
 <span data-ttu-id="f7428-148">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f7428-148">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f7428-149">Tipos de los parámetros de la operación.</span><span class="sxs-lookup"><span data-stu-id="f7428-149">The types of the parameters of the operation.</span></span>  
  
### <a name="replyaction"></a><span data-ttu-id="f7428-150">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="f7428-150">ReplyAction</span></span>  

 <span data-ttu-id="f7428-151">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="f7428-151">Data type: string</span></span>  
  
 <span data-ttu-id="f7428-152">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f7428-152">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f7428-153">El valor de la acción SOAP para el mensaje de respuesta de la operación.</span><span class="sxs-lookup"><span data-stu-id="f7428-153">The value of the SOAP action for the reply message of the operation.</span></span>  
  
### <a name="returntype"></a><span data-ttu-id="f7428-154">ReturnType</span><span class="sxs-lookup"><span data-stu-id="f7428-154">ReturnType</span></span>  

 <span data-ttu-id="f7428-155">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="f7428-155">Data type: string</span></span>  
  
 <span data-ttu-id="f7428-156">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f7428-156">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f7428-157">Tipo devuelto de la operación.</span><span class="sxs-lookup"><span data-stu-id="f7428-157">The return type of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7428-158">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7428-158">Requirements</span></span>  
  
|<span data-ttu-id="f7428-159">MOF</span><span class="sxs-lookup"><span data-stu-id="f7428-159">MOF</span></span>|<span data-ttu-id="f7428-160">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f7428-160">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f7428-161">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="f7428-161">Namespace</span></span>|<span data-ttu-id="f7428-162">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f7428-162">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f7428-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7428-163">See also</span></span>

- <xref:System.ServiceModel.Description.OperationDescription>
