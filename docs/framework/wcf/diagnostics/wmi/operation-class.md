---
title: Operation class
ms.date: 03/30/2017
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
ms.openlocfilehash: 9696a7f026e54afacb5ccbfa8703a2ba617a9f3d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "59973205"
---
# <a name="operation-class"></a><span data-ttu-id="fc63f-102">Operation class</span><span class="sxs-lookup"><span data-stu-id="fc63f-102">Operation class</span></span>
<span data-ttu-id="fc63f-103">Operación</span><span class="sxs-lookup"><span data-stu-id="fc63f-103">Operation</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc63f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc63f-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="fc63f-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="fc63f-105">Methods</span></span>  
 <span data-ttu-id="fc63f-106">La clase Operación no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="fc63f-106">The Operation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fc63f-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="fc63f-107">Properties</span></span>  
 <span data-ttu-id="fc63f-108">La clase Operación tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="fc63f-108">The Operation class has the following properties:</span></span>  
  
### <a name="action"></a><span data-ttu-id="fc63f-109">Acción</span><span class="sxs-lookup"><span data-stu-id="fc63f-109">Action</span></span>  
 <span data-ttu-id="fc63f-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="fc63f-110">Data type: string</span></span>  
  
 <span data-ttu-id="fc63f-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="fc63f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fc63f-112">La acción WS-Addressing del mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="fc63f-112">The WS-Addressing action of the request message.</span></span>  
  
### <a name="asyncpattern"></a><span data-ttu-id="fc63f-113">AsyncPattern</span><span class="sxs-lookup"><span data-stu-id="fc63f-113">AsyncPattern</span></span>  
 <span data-ttu-id="fc63f-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="fc63f-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="fc63f-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="fc63f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fc63f-116">Indica que una operación se implementa de forma asincrónica utilizando un `Begin`[Abrir/cerrar corchetes angulares] y `End`[entre corchetes angulares de apertura y cierre] el par de métodos en un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="fc63f-116">Indicates that an operation is implemented asynchronously using a `Begin`[open/close angle brackets] and `End`[open/close angle brackets] method pair in a service contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="fc63f-117">comportamientos</span><span class="sxs-lookup"><span data-stu-id="fc63f-117">Behaviors</span></span>  
 <span data-ttu-id="fc63f-118">Tipo de datos: Matriz de comportamiento</span><span class="sxs-lookup"><span data-stu-id="fc63f-118">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="fc63f-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="fc63f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fc63f-120">Los comportamientos asociados a esta operación.</span><span class="sxs-lookup"><span data-stu-id="fc63f-120">The behaviors associated with this operation.</span></span>  
  
### <a name="iscallback"></a><span data-ttu-id="fc63f-121">IsCallback</span><span class="sxs-lookup"><span data-stu-id="fc63f-121">IsCallback</span></span>  
 <span data-ttu-id="fc63f-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="fc63f-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="fc63f-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="fc63f-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fc63f-124">Verdadero cuando la operación es una operación de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="fc63f-124">True when the operation is a callback operation.</span></span>  
  
### <a name="isinitiating"></a><span data-ttu-id="fc63f-125">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="fc63f-125">IsInitiating</span></span>  
 <span data-ttu-id="fc63f-126">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="fc63f-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="fc63f-127">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="fc63f-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fc63f-128">Indica si el método implementa una operación que puede iniciar una sesión en el servidor.</span><span class="sxs-lookup"><span data-stu-id="fc63f-128">Indicates whether the method implements an operation that can initiate a session on the server.</span></span>  
  
### <a name="isoneway"></a><span data-ttu-id="fc63f-129">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="fc63f-129">IsOneWay</span></span>  
 <span data-ttu-id="fc63f-130">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="fc63f-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="fc63f-131">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="fc63f-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fc63f-132">Indica si una operación devuelve un mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="fc63f-132">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="isterminating"></a><span data-ttu-id="fc63f-133">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="fc63f-133">IsTerminating</span></span>  
 <span data-ttu-id="fc63f-134">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="fc63f-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="fc63f-135">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="fc63f-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fc63f-136">Indica si una operación devuelve un mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="fc63f-136">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="methodsignature"></a><span data-ttu-id="fc63f-137">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="fc63f-137">MethodSignature</span></span>  
 <span data-ttu-id="fc63f-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="fc63f-138">Data type: string</span></span>  
  
 <span data-ttu-id="fc63f-139">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="fc63f-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fc63f-140">La firma del método de la operación.</span><span class="sxs-lookup"><span data-stu-id="fc63f-140">The method signature of the operation.</span></span>  
  
### <a name="name"></a><span data-ttu-id="fc63f-141">Name</span><span class="sxs-lookup"><span data-stu-id="fc63f-141">Name</span></span>  
 <span data-ttu-id="fc63f-142">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="fc63f-142">Data type: string</span></span>  
  
 <span data-ttu-id="fc63f-143">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="fc63f-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fc63f-144">Nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="fc63f-144">The name of the operation.</span></span>  
  
### <a name="parametertypes"></a><span data-ttu-id="fc63f-145">ParameterTypes</span><span class="sxs-lookup"><span data-stu-id="fc63f-145">ParameterTypes</span></span>  
 <span data-ttu-id="fc63f-146">Tipo de datos: matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="fc63f-146">Data type: string array</span></span>  
  
 <span data-ttu-id="fc63f-147">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="fc63f-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fc63f-148">Tipos de los parámetros de la operación.</span><span class="sxs-lookup"><span data-stu-id="fc63f-148">The types of the parameters of the operation.</span></span>  
  
### <a name="replyaction"></a><span data-ttu-id="fc63f-149">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="fc63f-149">ReplyAction</span></span>  
 <span data-ttu-id="fc63f-150">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="fc63f-150">Data type: string</span></span>  
  
 <span data-ttu-id="fc63f-151">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="fc63f-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fc63f-152">El valor de la acción SOAP para el mensaje de respuesta de la operación.</span><span class="sxs-lookup"><span data-stu-id="fc63f-152">The value of the SOAP action for the reply message of the operation.</span></span>  
  
### <a name="returntype"></a><span data-ttu-id="fc63f-153">ReturnType</span><span class="sxs-lookup"><span data-stu-id="fc63f-153">ReturnType</span></span>  
 <span data-ttu-id="fc63f-154">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="fc63f-154">Data type: string</span></span>  
  
 <span data-ttu-id="fc63f-155">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="fc63f-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fc63f-156">Tipo devuelto de la operación.</span><span class="sxs-lookup"><span data-stu-id="fc63f-156">The return type of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc63f-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc63f-157">Requirements</span></span>  
  
|<span data-ttu-id="fc63f-158">MOF</span><span class="sxs-lookup"><span data-stu-id="fc63f-158">MOF</span></span>|<span data-ttu-id="fc63f-159">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="fc63f-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fc63f-160">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="fc63f-160">Namespace</span></span>|<span data-ttu-id="fc63f-161">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fc63f-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fc63f-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc63f-162">See also</span></span>

- <xref:System.ServiceModel.Description.OperationDescription>
