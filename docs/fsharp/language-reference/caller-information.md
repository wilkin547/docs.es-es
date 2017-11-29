---
title: "Información del llamador (F #)"
description: "Describe cómo utilizar atributos de argumento de información del autor de la llamada para obtener información del llamador de un método."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 04/25/2017
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a3dcc335-433b-4672-ac2d-ae6b11b816f3
ms.openlocfilehash: 533d2f0429ddb31e6d1dd7efca2f0760069a2945
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="caller-information"></a><span data-ttu-id="95604-104">Información del llamador</span><span class="sxs-lookup"><span data-stu-id="95604-104">Caller information</span></span>

<span data-ttu-id="95604-105">Mediante los atributos de información del llamador, se puede obtener información sobre el llamador de un método.</span><span class="sxs-lookup"><span data-stu-id="95604-105">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="95604-106">Puede obtener la ruta de acceso al código fuente, el número de línea en el código fuente y el nombre de miembro del llamador.</span><span class="sxs-lookup"><span data-stu-id="95604-106">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="95604-107">Esta información resulta útil para el seguimiento y la depuración, así como para crear herramientas de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="95604-107">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>

<span data-ttu-id="95604-108">Para obtener esta información, se usan los atributos que se aplican a los parámetros opcionales, que tienen valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="95604-108">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="95604-109">En la tabla siguiente se enumera los atributos de información del llamador que se definen en el [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) espacio de nombres:</span><span class="sxs-lookup"><span data-stu-id="95604-109">The following table lists the Caller Info attributes that are defined in the [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) namespace:</span></span>

|<span data-ttu-id="95604-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="95604-110">Attribute</span></span>|<span data-ttu-id="95604-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="95604-111">Description</span></span>|<span data-ttu-id="95604-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="95604-112">Type</span></span>|
|---------|-----------|----|
|[<span data-ttu-id="95604-113">CallerFilePath</span><span class="sxs-lookup"><span data-stu-id="95604-113">CallerFilePath</span></span>](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|<span data-ttu-id="95604-114">Ruta de acceso completa del archivo de código fuente que contiene el llamador.</span><span class="sxs-lookup"><span data-stu-id="95604-114">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="95604-115">Esta es la ruta de acceso en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="95604-115">This is the file path at compile time.</span></span>|`String`
|[<span data-ttu-id="95604-116">CallerLineNumber</span><span class="sxs-lookup"><span data-stu-id="95604-116">CallerLineNumber</span></span>](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|<span data-ttu-id="95604-117">Número de línea en el archivo de código fuente en el que se llama al método.</span><span class="sxs-lookup"><span data-stu-id="95604-117">Line number in the source file at which the method is called.</span></span>|`Integer`|
|[<span data-ttu-id="95604-118">CallerMemberName</span><span class="sxs-lookup"><span data-stu-id="95604-118">CallerMemberName</span></span>](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|<span data-ttu-id="95604-119">Método o nombre de propiedad del llamador.</span><span class="sxs-lookup"><span data-stu-id="95604-119">Method or property name of the caller.</span></span> <span data-ttu-id="95604-120">Vea la sección nombres de miembro más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="95604-120">See the Member Names section later in this topic.</span></span>|`String`|

## <a name="example"></a><span data-ttu-id="95604-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="95604-121">Example</span></span>

<span data-ttu-id="95604-122">En el ejemplo siguiente se muestra cómo puede usar estos atributos para realizar el seguimiento de un autor de llamada.</span><span class="sxs-lookup"><span data-stu-id="95604-122">The following example shows how you might use these attributes to trace a caller.</span></span>

```fsharp
open System.Diagnostics
open System.Runtime.CompilerServices

type Tracer() =
    member __.DoTrace(msg: string,
                      [<CallerMemberName>] ?memberName: string,
                      [<CallerFilePath>] ?path: string
                      [<CallerLineNumber>] ?line: int) =
        Trace.WriteLine(sprintf "Message: %s" message)
        match (memberName, path, line) with
        | Some m, Some p, Some l ->
            Trace.WriteLine(sprintf "Member name: %s" m)
            Trace.WriteLine(sprintf "Source file path: %s" p)
            Trace.WriteLine(sprintf "Source line number: %d" l)
        | _,_,_ -> ()
```

## <a name="remarks"></a><span data-ttu-id="95604-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="95604-123">Remarks</span></span>

<span data-ttu-id="95604-124">Atributos de información del autor de llamada solo pueden aplicarse a los parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="95604-124">Caller Info attributes can only be applied to optional parameters.</span></span> <span data-ttu-id="95604-125">Debe proporcionar un valor explícito para cada parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="95604-125">You must supply an explicit value for each optional parameter.</span></span> <span data-ttu-id="95604-126">Los atributos de información del llamador que el compilador escribir el valor adecuado para cada parámetro opcional decorada con un atributo de información del llamador.</span><span class="sxs-lookup"><span data-stu-id="95604-126">The Caller Info attributes cause the compiler to write the proper value for each optional parameter decorated with a Caller Info attribute.</span></span>

<span data-ttu-id="95604-127">Los valores de información del llamador se emiten como literales en el lenguaje intermedio (IL) en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="95604-127">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="95604-128">A diferencia de los resultados de la [StackTrace](/dotnet/api/system.diagnostics.stacktrace) propiedad para las excepciones, los resultados no se ven afectados por confusión.</span><span class="sxs-lookup"><span data-stu-id="95604-128">Unlike the results of the [StackTrace](/dotnet/api/system.diagnostics.stacktrace) property for exceptions, the results aren't affected by obfuscation.</span></span>

<span data-ttu-id="95604-129">Puede proporcionar explícitamente los argumentos opcionales para controlar la información del llamador u ocultarla.</span><span class="sxs-lookup"><span data-stu-id="95604-129">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

## <a name="member-names"></a><span data-ttu-id="95604-130">Nombres de miembro</span><span class="sxs-lookup"><span data-stu-id="95604-130">Member names</span></span>

<span data-ttu-id="95604-131">Puede usar el [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) atributo para evitar especificar el nombre de miembro como un `String` argumento para el método llamado.</span><span class="sxs-lookup"><span data-stu-id="95604-131">You can use the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="95604-132">Mediante esta técnica, se evita el problema que cambiar el nombre de refactorización no cambia el `String` valores.</span><span class="sxs-lookup"><span data-stu-id="95604-132">By using this technique, you avoid the problem that Rename Refactoring doesn't change the `String` values.</span></span> <span data-ttu-id="95604-133">Esta ventaja es especialmente útil para las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="95604-133">This benefit is especially useful for the following tasks:</span></span>

* <span data-ttu-id="95604-134">Usar el seguimiento y las rutinas de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="95604-134">Using tracing and diagnostic routines.</span></span>
* <span data-ttu-id="95604-135">Implementar la [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) interfaz cuando se enlazan datos.</span><span class="sxs-lookup"><span data-stu-id="95604-135">Implementing the [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) interface when binding data.</span></span> <span data-ttu-id="95604-136">Esta interfaz permite que la propiedad de un objeto notifique a un control enlazado que la propiedad ha cambiado, de forma que el control pueda mostrar información actualizada.</span><span class="sxs-lookup"><span data-stu-id="95604-136">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="95604-137">Sin el [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) atributo, debe especificar el nombre de propiedad como un literal.</span><span class="sxs-lookup"><span data-stu-id="95604-137">Without the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="95604-138">El siguiente gráfico muestra al miembro nombres que se devuelven cuando se usa el atributo CallerMemberName.</span><span class="sxs-lookup"><span data-stu-id="95604-138">The following chart shows the member names that are returned when you use the CallerMemberName attribute.</span></span>

|<span data-ttu-id="95604-139">Las llamadas se producen en</span><span class="sxs-lookup"><span data-stu-id="95604-139">Calls occurs within</span></span>|<span data-ttu-id="95604-140">Resultado del nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="95604-140">Member name result</span></span>|
|-------------------|------------------|
|<span data-ttu-id="95604-141">Método, propiedad o evento</span><span class="sxs-lookup"><span data-stu-id="95604-141">Method, property, or event</span></span>|<span data-ttu-id="95604-142">Nombre del método, propiedad o evento en el que se originó la llamada.</span><span class="sxs-lookup"><span data-stu-id="95604-142">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="95604-143">Constructor</span><span class="sxs-lookup"><span data-stu-id="95604-143">Constructor</span></span>|<span data-ttu-id="95604-144">Cadena ".ctor"</span><span class="sxs-lookup"><span data-stu-id="95604-144">The string ".ctor"</span></span>|
|<span data-ttu-id="95604-145">Constructor estático</span><span class="sxs-lookup"><span data-stu-id="95604-145">Static constructor</span></span>|<span data-ttu-id="95604-146">Cadena ".cctor"</span><span class="sxs-lookup"><span data-stu-id="95604-146">The string ".cctor"</span></span>|
|<span data-ttu-id="95604-147">Destructor</span><span class="sxs-lookup"><span data-stu-id="95604-147">Destructor</span></span>|<span data-ttu-id="95604-148">Cadena "Finalize"</span><span class="sxs-lookup"><span data-stu-id="95604-148">The string "Finalize"</span></span>|
|<span data-ttu-id="95604-149">Conversiones u operadores definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="95604-149">User-defined operators or conversions</span></span>|<span data-ttu-id="95604-150">Nombre generado para el miembro, por ejemplo, "op_Addition".</span><span class="sxs-lookup"><span data-stu-id="95604-150">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="95604-151">Constructor de atributo</span><span class="sxs-lookup"><span data-stu-id="95604-151">Attribute constructor</span></span>|<span data-ttu-id="95604-152">Nombre del miembro al que se aplica el atributo.</span><span class="sxs-lookup"><span data-stu-id="95604-152">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="95604-153">Si el atributo es cualquier elemento dentro de un miembro (como un parámetro, un valor devuelto o un parámetro de tipo genérico), el resultado es el nombre del miembro asociado a este elemento.</span><span class="sxs-lookup"><span data-stu-id="95604-153">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="95604-154">Ningún miembro contenedor (por ejemplo, nivel de ensamblado o atributos que se aplican a tipos)</span><span class="sxs-lookup"><span data-stu-id="95604-154">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="95604-155">El valor predeterminado del parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="95604-155">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="95604-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="95604-156">See also</span></span>
 [<span data-ttu-id="95604-157">Atributos</span><span class="sxs-lookup"><span data-stu-id="95604-157">Attributes</span></span>](attributes.md)  
 [<span data-ttu-id="95604-158">Argumentos con nombre</span><span class="sxs-lookup"><span data-stu-id="95604-158">Named arguments</span></span>](parameters-and-arguments.md#named-arguments)  
 [<span data-ttu-id="95604-159">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="95604-159">Optional parameters</span></span>](parameters-and-arguments.md#optional-parameters)  
