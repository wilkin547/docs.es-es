---
title: 'Información del llamador (F #)'
description: Describe cómo utilizar atributos de argumento de información del autor de llamada para obtener información del llamador de un método.
ms.date: 04/25/2017
ms.openlocfilehash: 0f2f4b16804d9156d234cc29d1f72ebe80a5b556
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47216375"
---
# <a name="caller-information"></a><span data-ttu-id="e4d61-103">Información del llamador</span><span class="sxs-lookup"><span data-stu-id="e4d61-103">Caller information</span></span>

<span data-ttu-id="e4d61-104">Mediante los atributos de información del llamador, se puede obtener información sobre el llamador de un método.</span><span class="sxs-lookup"><span data-stu-id="e4d61-104">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="e4d61-105">Puede obtener la ruta de acceso al código fuente, el número de línea en el código fuente y el nombre de miembro del llamador.</span><span class="sxs-lookup"><span data-stu-id="e4d61-105">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="e4d61-106">Esta información resulta útil para el seguimiento y la depuración, así como para crear herramientas de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="e4d61-106">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>

<span data-ttu-id="e4d61-107">Para obtener esta información, se usan los atributos que se aplican a los parámetros opcionales, que tienen valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="e4d61-107">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="e4d61-108">En la tabla siguiente se enumera los atributos de información del llamador que se definen en el [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) espacio de nombres:</span><span class="sxs-lookup"><span data-stu-id="e4d61-108">The following table lists the Caller Info attributes that are defined in the [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) namespace:</span></span>

|<span data-ttu-id="e4d61-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="e4d61-109">Attribute</span></span>|<span data-ttu-id="e4d61-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4d61-110">Description</span></span>|<span data-ttu-id="e4d61-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="e4d61-111">Type</span></span>|
|---------|-----------|----|
|[<span data-ttu-id="e4d61-112">CallerFilePath</span><span class="sxs-lookup"><span data-stu-id="e4d61-112">CallerFilePath</span></span>](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|<span data-ttu-id="e4d61-113">Ruta de acceso completa del archivo de código fuente que contiene el llamador.</span><span class="sxs-lookup"><span data-stu-id="e4d61-113">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="e4d61-114">Esta es la ruta de acceso en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="e4d61-114">This is the file path at compile time.</span></span>|`String`
|[<span data-ttu-id="e4d61-115">CallerLineNumber</span><span class="sxs-lookup"><span data-stu-id="e4d61-115">CallerLineNumber</span></span>](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|<span data-ttu-id="e4d61-116">Número de línea en el archivo de código fuente en el que se llama al método.</span><span class="sxs-lookup"><span data-stu-id="e4d61-116">Line number in the source file at which the method is called.</span></span>|`Integer`|
|[<span data-ttu-id="e4d61-117">CallerMemberName</span><span class="sxs-lookup"><span data-stu-id="e4d61-117">CallerMemberName</span></span>](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|<span data-ttu-id="e4d61-118">Método o nombre de propiedad del llamador.</span><span class="sxs-lookup"><span data-stu-id="e4d61-118">Method or property name of the caller.</span></span> <span data-ttu-id="e4d61-119">Consulte la sección de los nombres de miembro más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="e4d61-119">See the Member Names section later in this topic.</span></span>|`String`|

## <a name="example"></a><span data-ttu-id="e4d61-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e4d61-120">Example</span></span>

<span data-ttu-id="e4d61-121">El ejemplo siguiente muestra cómo puede usar estos atributos para realizar un seguimiento de un autor de llamada.</span><span class="sxs-lookup"><span data-stu-id="e4d61-121">The following example shows how you might use these attributes to trace a caller.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="e4d61-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e4d61-122">Remarks</span></span>

<span data-ttu-id="e4d61-123">Atributos de información del autor de llamada solo pueden aplicarse a los parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="e4d61-123">Caller Info attributes can only be applied to optional parameters.</span></span> <span data-ttu-id="e4d61-124">Debe proporcionar un valor explícito para cada parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="e4d61-124">You must supply an explicit value for each optional parameter.</span></span> <span data-ttu-id="e4d61-125">Los atributos de información del llamador que el compilador escribir el valor adecuado para cada parámetro opcional representado con un atributo de información del llamador.</span><span class="sxs-lookup"><span data-stu-id="e4d61-125">The Caller Info attributes cause the compiler to write the proper value for each optional parameter decorated with a Caller Info attribute.</span></span>

<span data-ttu-id="e4d61-126">Los valores de información del llamador se emiten como literales en el lenguaje intermedio (IL) en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="e4d61-126">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="e4d61-127">A diferencia de los resultados de la [StackTrace](/dotnet/api/system.diagnostics.stacktrace) propiedad para las excepciones, los resultados no se ven afectados por ofuscación.</span><span class="sxs-lookup"><span data-stu-id="e4d61-127">Unlike the results of the [StackTrace](/dotnet/api/system.diagnostics.stacktrace) property for exceptions, the results aren't affected by obfuscation.</span></span>

<span data-ttu-id="e4d61-128">Puede proporcionar explícitamente los argumentos opcionales para controlar la información del llamador u ocultarla.</span><span class="sxs-lookup"><span data-stu-id="e4d61-128">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

## <a name="member-names"></a><span data-ttu-id="e4d61-129">Nombres de miembro</span><span class="sxs-lookup"><span data-stu-id="e4d61-129">Member names</span></span>

<span data-ttu-id="e4d61-130">Puede usar el [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) atributo para evitar especificar el nombre de miembro como un `String` argumento al método llamado.</span><span class="sxs-lookup"><span data-stu-id="e4d61-130">You can use the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="e4d61-131">Mediante esta técnica, se evita el problema que cambiar el nombre de refactorización no cambia el `String` valores.</span><span class="sxs-lookup"><span data-stu-id="e4d61-131">By using this technique, you avoid the problem that Rename Refactoring doesn't change the `String` values.</span></span> <span data-ttu-id="e4d61-132">Esta ventaja es especialmente útil para las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="e4d61-132">This benefit is especially useful for the following tasks:</span></span>

* <span data-ttu-id="e4d61-133">Usar el seguimiento y las rutinas de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="e4d61-133">Using tracing and diagnostic routines.</span></span>
* <span data-ttu-id="e4d61-134">Implementar el [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) al enlazar datos de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="e4d61-134">Implementing the [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) interface when binding data.</span></span> <span data-ttu-id="e4d61-135">Esta interfaz permite que la propiedad de un objeto notifique a un control enlazado que la propiedad ha cambiado, de forma que el control pueda mostrar información actualizada.</span><span class="sxs-lookup"><span data-stu-id="e4d61-135">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="e4d61-136">Sin el [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) atributo, debe especificar el nombre de propiedad como un literal.</span><span class="sxs-lookup"><span data-stu-id="e4d61-136">Without the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="e4d61-137">El siguiente gráfico muestra al miembro de los nombres que se devuelven cuando se usa el atributo CallerMemberName.</span><span class="sxs-lookup"><span data-stu-id="e4d61-137">The following chart shows the member names that are returned when you use the CallerMemberName attribute.</span></span>

|<span data-ttu-id="e4d61-138">Las llamadas se producen en</span><span class="sxs-lookup"><span data-stu-id="e4d61-138">Calls occurs within</span></span>|<span data-ttu-id="e4d61-139">Resultado del nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="e4d61-139">Member name result</span></span>|
|-------------------|------------------|
|<span data-ttu-id="e4d61-140">Método, propiedad o evento</span><span class="sxs-lookup"><span data-stu-id="e4d61-140">Method, property, or event</span></span>|<span data-ttu-id="e4d61-141">Nombre del método, propiedad o evento en el que se originó la llamada.</span><span class="sxs-lookup"><span data-stu-id="e4d61-141">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="e4d61-142">Constructor</span><span class="sxs-lookup"><span data-stu-id="e4d61-142">Constructor</span></span>|<span data-ttu-id="e4d61-143">Cadena ".ctor"</span><span class="sxs-lookup"><span data-stu-id="e4d61-143">The string ".ctor"</span></span>|
|<span data-ttu-id="e4d61-144">Constructor estático</span><span class="sxs-lookup"><span data-stu-id="e4d61-144">Static constructor</span></span>|<span data-ttu-id="e4d61-145">Cadena ".cctor"</span><span class="sxs-lookup"><span data-stu-id="e4d61-145">The string ".cctor"</span></span>|
|<span data-ttu-id="e4d61-146">Destructor</span><span class="sxs-lookup"><span data-stu-id="e4d61-146">Destructor</span></span>|<span data-ttu-id="e4d61-147">Cadena "Finalize"</span><span class="sxs-lookup"><span data-stu-id="e4d61-147">The string "Finalize"</span></span>|
|<span data-ttu-id="e4d61-148">Conversiones u operadores definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="e4d61-148">User-defined operators or conversions</span></span>|<span data-ttu-id="e4d61-149">Nombre generado para el miembro, por ejemplo, "op_Addition".</span><span class="sxs-lookup"><span data-stu-id="e4d61-149">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="e4d61-150">Constructor de atributo</span><span class="sxs-lookup"><span data-stu-id="e4d61-150">Attribute constructor</span></span>|<span data-ttu-id="e4d61-151">Nombre del miembro al que se aplica el atributo.</span><span class="sxs-lookup"><span data-stu-id="e4d61-151">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="e4d61-152">Si el atributo es cualquier elemento dentro de un miembro (como un parámetro, un valor devuelto o un parámetro de tipo genérico), el resultado es el nombre del miembro asociado a este elemento.</span><span class="sxs-lookup"><span data-stu-id="e4d61-152">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="e4d61-153">Ningún miembro contenedor (por ejemplo, nivel de ensamblado o atributos que se aplican a tipos)</span><span class="sxs-lookup"><span data-stu-id="e4d61-153">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="e4d61-154">El valor predeterminado del parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="e4d61-154">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="e4d61-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4d61-155">See also</span></span>

- [<span data-ttu-id="e4d61-156">Atributos</span><span class="sxs-lookup"><span data-stu-id="e4d61-156">Attributes</span></span>](attributes.md)  
- [<span data-ttu-id="e4d61-157">Argumentos con nombre</span><span class="sxs-lookup"><span data-stu-id="e4d61-157">Named arguments</span></span>](parameters-and-arguments.md#named-arguments)  
- [<span data-ttu-id="e4d61-158">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="e4d61-158">Optional parameters</span></span>](parameters-and-arguments.md#optional-parameters)  
