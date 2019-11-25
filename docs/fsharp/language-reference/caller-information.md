---
title: Información del llamador
description: Describe cómo usar los atributos de argumento de información del llamador para obtener información del llamador de un método.
ms.date: 11/04/2019
ms.openlocfilehash: d995b37149277b7c7d1b6217ee484d3c90a7f8b3
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976797"
---
# <a name="caller-information"></a><span data-ttu-id="5cb65-103">Información del llamador</span><span class="sxs-lookup"><span data-stu-id="5cb65-103">Caller information</span></span>

<span data-ttu-id="5cb65-104">Mediante los atributos de información del llamador, se puede obtener información sobre el llamador de un método.</span><span class="sxs-lookup"><span data-stu-id="5cb65-104">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="5cb65-105">Puede obtener la ruta de acceso al código fuente, el número de línea en el código fuente y el nombre de miembro del llamador.</span><span class="sxs-lookup"><span data-stu-id="5cb65-105">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="5cb65-106">Esta información resulta útil para el seguimiento y la depuración, así como para crear herramientas de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="5cb65-106">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>

<span data-ttu-id="5cb65-107">Para obtener esta información, se usan los atributos que se aplican a los parámetros opcionales, que tienen valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="5cb65-107">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="5cb65-108">En la tabla siguiente se enumeran los atributos de información del llamador que se definen en el espacio de nombres [System. Runtime. CompilerServices](/dotnet/api/system.runtime.compilerservices) :</span><span class="sxs-lookup"><span data-stu-id="5cb65-108">The following table lists the Caller Info attributes that are defined in the [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) namespace:</span></span>

|<span data-ttu-id="5cb65-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="5cb65-109">Attribute</span></span>|<span data-ttu-id="5cb65-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="5cb65-110">Description</span></span>|<span data-ttu-id="5cb65-111">Type</span><span class="sxs-lookup"><span data-stu-id="5cb65-111">Type</span></span>|
|---------|-----------|----|
|[<span data-ttu-id="5cb65-112">CallerFilePath</span><span class="sxs-lookup"><span data-stu-id="5cb65-112">CallerFilePath</span></span>](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|<span data-ttu-id="5cb65-113">Ruta de acceso completa del archivo de código fuente que contiene el llamador.</span><span class="sxs-lookup"><span data-stu-id="5cb65-113">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="5cb65-114">Esta es la ruta de acceso en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="5cb65-114">This is the file path at compile time.</span></span>|`String`
|[<span data-ttu-id="5cb65-115">CallerLineNumber</span><span class="sxs-lookup"><span data-stu-id="5cb65-115">CallerLineNumber</span></span>](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|<span data-ttu-id="5cb65-116">Número de línea en el archivo de código fuente en el que se llama al método.</span><span class="sxs-lookup"><span data-stu-id="5cb65-116">Line number in the source file at which the method is called.</span></span>|`Integer`|
|[<span data-ttu-id="5cb65-117">CallerMemberName</span><span class="sxs-lookup"><span data-stu-id="5cb65-117">CallerMemberName</span></span>](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|<span data-ttu-id="5cb65-118">Método o nombre de propiedad del llamador.</span><span class="sxs-lookup"><span data-stu-id="5cb65-118">Method or property name of the caller.</span></span> <span data-ttu-id="5cb65-119">Vea la sección nombres de miembro más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="5cb65-119">See the Member Names section later in this topic.</span></span>|`String`|

## <a name="example"></a><span data-ttu-id="5cb65-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5cb65-120">Example</span></span>

<span data-ttu-id="5cb65-121">En el ejemplo siguiente se muestra cómo puede utilizar estos atributos para realizar el seguimiento de un llamador.</span><span class="sxs-lookup"><span data-stu-id="5cb65-121">The following example shows how you might use these attributes to trace a caller.</span></span>

```fsharp
open System.Diagnostics
open System.Runtime.CompilerServices
open System.Runtime.InteropServices

type Tracer() =
    member _.DoTrace(message: string,
                      [<CallerMemberName; Optional; DefaultParameterValue("")>] memberName: string,
                      [<CallerFilePath; Optional; DefaultParameterValue("")>] path: string,
                      [<CallerLineNumber; Optional; DefaultParameterValue(0)>] line: int) =
        Trace.WriteLine(sprintf "Message: %s" message)
        Trace.WriteLine(sprintf "Member name: %s" memberName)
        Trace.WriteLine(sprintf "Source file path: %s" path)
        Trace.WriteLine(sprintf "Source line number: %d" line)
```

## <a name="remarks"></a><span data-ttu-id="5cb65-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5cb65-122">Remarks</span></span>

<span data-ttu-id="5cb65-123">Los atributos de información del llamador solo se pueden aplicar a los parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="5cb65-123">Caller Info attributes can only be applied to optional parameters.</span></span> <span data-ttu-id="5cb65-124">Los atributos de información del llamador hacen que el compilador escriba el valor adecuado para cada parámetro opcional decorado con un atributo de información del llamador.</span><span class="sxs-lookup"><span data-stu-id="5cb65-124">The Caller Info attributes cause the compiler to write the proper value for each optional parameter decorated with a Caller Info attribute.</span></span>

<span data-ttu-id="5cb65-125">Los valores de información del llamador se emiten como literales en el lenguaje intermedio (IL) en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="5cb65-125">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="5cb65-126">A diferencia de los resultados de la propiedad [StackTrace](/dotnet/api/system.diagnostics.stacktrace) para las excepciones, los resultados no se ven afectados por la ofuscación.</span><span class="sxs-lookup"><span data-stu-id="5cb65-126">Unlike the results of the [StackTrace](/dotnet/api/system.diagnostics.stacktrace) property for exceptions, the results aren't affected by obfuscation.</span></span>

<span data-ttu-id="5cb65-127">Puede proporcionar explícitamente los argumentos opcionales para controlar la información del llamador u ocultarla.</span><span class="sxs-lookup"><span data-stu-id="5cb65-127">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

## <a name="member-names"></a><span data-ttu-id="5cb65-128">Nombres de miembro</span><span class="sxs-lookup"><span data-stu-id="5cb65-128">Member names</span></span>

<span data-ttu-id="5cb65-129">Puede usar el atributo [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) para evitar especificar el nombre de miembro como un argumento `String` para el método llamado.</span><span class="sxs-lookup"><span data-stu-id="5cb65-129">You can use the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="5cb65-130">Mediante esta técnica, se evita el problema de que la refactorización de cambio de nombre no cambie los valores de `String`.</span><span class="sxs-lookup"><span data-stu-id="5cb65-130">By using this technique, you avoid the problem that Rename Refactoring doesn't change the `String` values.</span></span> <span data-ttu-id="5cb65-131">Esta ventaja es especialmente útil para las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="5cb65-131">This benefit is especially useful for the following tasks:</span></span>

- <span data-ttu-id="5cb65-132">Usar el seguimiento y las rutinas de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="5cb65-132">Using tracing and diagnostic routines.</span></span>
- <span data-ttu-id="5cb65-133">Implementar la interfaz [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) al enlazar datos.</span><span class="sxs-lookup"><span data-stu-id="5cb65-133">Implementing the [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) interface when binding data.</span></span> <span data-ttu-id="5cb65-134">Esta interfaz permite que la propiedad de un objeto notifique a un control enlazado que la propiedad ha cambiado, de forma que el control pueda mostrar información actualizada.</span><span class="sxs-lookup"><span data-stu-id="5cb65-134">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="5cb65-135">Sin el atributo [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) , debe especificar el nombre de la propiedad como un literal.</span><span class="sxs-lookup"><span data-stu-id="5cb65-135">Without the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="5cb65-136">En el gráfico siguiente se muestran los nombres de miembro que se devuelven cuando se usa el atributo CallerMemberName.</span><span class="sxs-lookup"><span data-stu-id="5cb65-136">The following chart shows the member names that are returned when you use the CallerMemberName attribute.</span></span>

|<span data-ttu-id="5cb65-137">Las llamadas se producen en</span><span class="sxs-lookup"><span data-stu-id="5cb65-137">Calls occurs within</span></span>|<span data-ttu-id="5cb65-138">Resultado del nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="5cb65-138">Member name result</span></span>|
|-------------------|------------------|
|<span data-ttu-id="5cb65-139">Método, propiedad o evento</span><span class="sxs-lookup"><span data-stu-id="5cb65-139">Method, property, or event</span></span>|<span data-ttu-id="5cb65-140">Nombre del método, propiedad o evento en el que se originó la llamada.</span><span class="sxs-lookup"><span data-stu-id="5cb65-140">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="5cb65-141">Constructor</span><span class="sxs-lookup"><span data-stu-id="5cb65-141">Constructor</span></span>|<span data-ttu-id="5cb65-142">Cadena ".ctor"</span><span class="sxs-lookup"><span data-stu-id="5cb65-142">The string ".ctor"</span></span>|
|<span data-ttu-id="5cb65-143">Constructor estático</span><span class="sxs-lookup"><span data-stu-id="5cb65-143">Static constructor</span></span>|<span data-ttu-id="5cb65-144">Cadena ".cctor"</span><span class="sxs-lookup"><span data-stu-id="5cb65-144">The string ".cctor"</span></span>|
|<span data-ttu-id="5cb65-145">Destructor</span><span class="sxs-lookup"><span data-stu-id="5cb65-145">Destructor</span></span>|<span data-ttu-id="5cb65-146">Cadena "Finalize"</span><span class="sxs-lookup"><span data-stu-id="5cb65-146">The string "Finalize"</span></span>|
|<span data-ttu-id="5cb65-147">Conversiones u operadores definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="5cb65-147">User-defined operators or conversions</span></span>|<span data-ttu-id="5cb65-148">Nombre generado para el miembro, por ejemplo, "op_Addition".</span><span class="sxs-lookup"><span data-stu-id="5cb65-148">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="5cb65-149">Constructor de atributo</span><span class="sxs-lookup"><span data-stu-id="5cb65-149">Attribute constructor</span></span>|<span data-ttu-id="5cb65-150">Nombre del miembro al que se aplica el atributo.</span><span class="sxs-lookup"><span data-stu-id="5cb65-150">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="5cb65-151">Si el atributo es cualquier elemento dentro de un miembro (como un parámetro, un valor devuelto o un parámetro de tipo genérico), el resultado es el nombre del miembro asociado a este elemento.</span><span class="sxs-lookup"><span data-stu-id="5cb65-151">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="5cb65-152">Ningún miembro contenedor (por ejemplo, nivel de ensamblado o atributos que se aplican a tipos)</span><span class="sxs-lookup"><span data-stu-id="5cb65-152">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="5cb65-153">El valor predeterminado del parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="5cb65-153">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="5cb65-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="5cb65-154">See also</span></span>

- [<span data-ttu-id="5cb65-155">Atributos</span><span class="sxs-lookup"><span data-stu-id="5cb65-155">Attributes</span></span>](attributes.md)
- [<span data-ttu-id="5cb65-156">Argumentos con nombre</span><span class="sxs-lookup"><span data-stu-id="5cb65-156">Named arguments</span></span>](parameters-and-arguments.md#named-arguments)
- [<span data-ttu-id="5cb65-157">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="5cb65-157">Optional parameters</span></span>](parameters-and-arguments.md#optional-parameters)
