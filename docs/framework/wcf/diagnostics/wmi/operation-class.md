---
title: Operation class
ms.date: 03/30/2017
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
ms.openlocfilehash: 9696a7f026e54afacb5ccbfa8703a2ba617a9f3d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165085"
---
# <a name="operation-class"></a><span data-ttu-id="bfe8a-102">Operation class</span><span class="sxs-lookup"><span data-stu-id="bfe8a-102">Operation class</span></span>
<span data-ttu-id="bfe8a-103">Operación</span><span class="sxs-lookup"><span data-stu-id="bfe8a-103">Operation</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfe8a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bfe8a-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="bfe8a-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="bfe8a-105">Methods</span></span>  
 <span data-ttu-id="bfe8a-106">La clase Operación no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="bfe8a-106">The Operation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bfe8a-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="bfe8a-107">Properties</span></span>  
 <span data-ttu-id="bfe8a-108">La clase Operación tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="bfe8a-108">The Operation class has the following properties:</span></span>  
  
### <a name="action"></a><span data-ttu-id="bfe8a-109">Acción</span><span class="sxs-lookup"><span data-stu-id="bfe8a-109">Action</span></span>  
 <span data-ttu-id="bfe8a-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bfe8a-110">Data type: string</span></span>  
  
 <span data-ttu-id="bfe8a-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bfe8a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bfe8a-112">La acción WS-Addressing del mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="bfe8a-112">The WS-Addressing action of the request message.</span></span>  
  
### <a name="asyncpattern"></a><span data-ttu-id="bfe8a-113">AsyncPattern</span><span class="sxs-lookup"><span data-stu-id="bfe8a-113">AsyncPattern</span></span>  
 <span data-ttu-id="bfe8a-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="bfe8a-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="bfe8a-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bfe8a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bfe8a-116">Indica que una operación se implementa de forma asincrónica utilizando un `Begin`[Abrir/cerrar corchetes angulares] y `End`[entre corchetes angulares de apertura y cierre] el par de métodos en un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="bfe8a-116">Indicates that an operation is implemented asynchronously using a `Begin`[open/close angle brackets] and `End`[open/close angle brackets] method pair in a service contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="bfe8a-117">comportamientos</span><span class="sxs-lookup"><span data-stu-id="bfe8a-117">Behaviors</span></span>  
 <span data-ttu-id="bfe8a-118">Tipo de datos: Matriz de comportamiento</span><span class="sxs-lookup"><span data-stu-id="bfe8a-118">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="bfe8a-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bfe8a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bfe8a-120">Los comportamientos asociados a esta operación.</span><span class="sxs-lookup"><span data-stu-id="bfe8a-120">The behaviors associated with this operation.</span></span>  
  
### <a name="iscallback"></a><span data-ttu-id="bfe8a-121">IsCallback</span><span class="sxs-lookup"><span data-stu-id="bfe8a-121">IsCallback</span></span>  
 <span data-ttu-id="bfe8a-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="bfe8a-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="bfe8a-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bfe8a-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bfe8a-124">Verdadero cuando la operación es una operación de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="bfe8a-124">True when the operation is a callback operation.</span></span>  
  
### <a name="isinitiating"></a><span data-ttu-id="bfe8a-125">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="bfe8a-125">IsInitiating</span></span>  
 <span data-ttu-id="bfe8a-126">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="bfe8a-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="bfe8a-127">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bfe8a-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bfe8a-128">Indica si el método implementa una operación que puede iniciar una sesión en el servidor.</span><span class="sxs-lookup"><span data-stu-id="bfe8a-128">Indicates whether the method implements an operation that can initiate a session on the server.</span></span>  
  
### <a name="isoneway"></a><span data-ttu-id="bfe8a-129">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="bfe8a-129">IsOneWay</span></span>  
 <span data-ttu-id="bfe8a-130">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="bfe8a-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="bfe8a-131">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bfe8a-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bfe8a-132">Indica si una operación devuelve un mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="bfe8a-132">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="isterminating"></a><span data-ttu-id="bfe8a-133">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="bfe8a-133">IsTerminating</span></span>  
 <span data-ttu-id="bfe8a-134">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="bfe8a-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="bfe8a-135">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bfe8a-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bfe8a-136">Indica si una operación devuelve un mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="bfe8a-136">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="methodsignature"></a><span data-ttu-id="bfe8a-137">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="bfe8a-137">MethodSignature</span></span>  
 <span data-ttu-id="bfe8a-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bfe8a-138">Data type: string</span></span>  
  
 <span data-ttu-id="bfe8a-139">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bfe8a-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bfe8a-140">La firma del método de la operación.</span><span class="sxs-lookup"><span data-stu-id="bfe8a-140">The method signature of the operation.</span></span>  
  
### <a name="name"></a><span data-ttu-id="bfe8a-141">Name</span><span class="sxs-lookup"><span data-stu-id="bfe8a-141">Name</span></span>  
 <span data-ttu-id="bfe8a-142">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bfe8a-142">Data type: string</span></span>  
  
 <span data-ttu-id="bfe8a-143">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bfe8a-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bfe8a-144">Nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="bfe8a-144">The name of the operation.</span></span>  
  
### <a name="parametertypes"></a><span data-ttu-id="bfe8a-145">ParameterTypes</span><span class="sxs-lookup"><span data-stu-id="bfe8a-145">ParameterTypes</span></span>  
 <span data-ttu-id="bfe8a-146">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="bfe8a-146">Data type: string array</span></span>  
  
 <span data-ttu-id="bfe8a-147">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bfe8a-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bfe8a-148">Tipos de los parámetros de la operación.</span><span class="sxs-lookup"><span data-stu-id="bfe8a-148">The types of the parameters of the operation.</span></span>  
  
### <a name="replyaction"></a><span data-ttu-id="bfe8a-149">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="bfe8a-149">ReplyAction</span></span>  
 <span data-ttu-id="bfe8a-150">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bfe8a-150">Data type: string</span></span>  
  
 <span data-ttu-id="bfe8a-151">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bfe8a-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bfe8a-152">El valor de la acción SOAP para el mensaje de respuesta de la operación.</span><span class="sxs-lookup"><span data-stu-id="bfe8a-152">The value of the SOAP action for the reply message of the operation.</span></span>  
  
### <a name="returntype"></a><span data-ttu-id="bfe8a-153">ReturnType</span><span class="sxs-lookup"><span data-stu-id="bfe8a-153">ReturnType</span></span>  
 <span data-ttu-id="bfe8a-154">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bfe8a-154">Data type: string</span></span>  
  
 <span data-ttu-id="bfe8a-155">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bfe8a-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bfe8a-156">Tipo devuelto de la operación.</span><span class="sxs-lookup"><span data-stu-id="bfe8a-156">The return type of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfe8a-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bfe8a-157">Requirements</span></span>  
  
|<span data-ttu-id="bfe8a-158">MOF</span><span class="sxs-lookup"><span data-stu-id="bfe8a-158">MOF</span></span>|<span data-ttu-id="bfe8a-159">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="bfe8a-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bfe8a-160">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="bfe8a-160">Namespace</span></span>|<span data-ttu-id="bfe8a-161">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="bfe8a-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bfe8a-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfe8a-162">See also</span></span>

- <xref:System.ServiceModel.Description.OperationDescription>
