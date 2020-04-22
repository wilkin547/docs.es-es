---
title: 'Atributos reservados de C#: seguimiento de la información del autor de la llamada'
ms.date: 04/09/2020
description: Estos atributos indican al compilador que genere información sobre el código que llama a un miembro. Use CallerFilePath, CallerLineNumber y CallerMemberName para proporcionar información de seguimiento detallada.
ms.openlocfilehash: ee061d4cae35bdcc0b89007e360e94fee8c5f87c
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389827"
---
# <a name="reserved-attributes-determine-caller-information"></a><span data-ttu-id="f9534-104">Atributos reservados: determinación de la información del autor de la llamada</span><span class="sxs-lookup"><span data-stu-id="f9534-104">Reserved attributes: Determine caller information</span></span>

<span data-ttu-id="f9534-105">Mediante los atributos de información, se obtiene información sobre el autor de la llamada a un método.</span><span class="sxs-lookup"><span data-stu-id="f9534-105">Using info attributes, you obtain information about the caller to a method.</span></span> <span data-ttu-id="f9534-106">Se obtiene la ruta de acceso al código fuente, el número de línea del código fuente y el nombre de miembro del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f9534-106">You obtain the file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="f9534-107">Para obtener la información del llamador del miembro, use los atributos que se aplican a los parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="f9534-107">To obtain member caller information, you use attributes that are applied to optional parameters.</span></span> <span data-ttu-id="f9534-108">Cada parámetro opcional especifica un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f9534-108">Each optional parameter specifies a default value.</span></span> <span data-ttu-id="f9534-109">En la tabla siguiente se enumeran los atributos de información del llamador que se definen en el espacio de nombres <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="f9534-109">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>

|<span data-ttu-id="f9534-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="f9534-110">Attribute</span></span>|<span data-ttu-id="f9534-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9534-111">Description</span></span>|<span data-ttu-id="f9534-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="f9534-112">Type</span></span>|
|---|---|---|
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="f9534-113">Ruta de acceso completa del archivo de código fuente que contiene el llamador.</span><span class="sxs-lookup"><span data-stu-id="f9534-113">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="f9534-114">La ruta de acceso completa es la ruta de acceso en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="f9534-114">The full path is the path at compile time.</span></span>|`String`|
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="f9534-115">Número de línea del archivo de código fuente desde el que se llama al método.</span><span class="sxs-lookup"><span data-stu-id="f9534-115">Line number in the source file from which the method is called.</span></span>|`Integer`|
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="f9534-116">Nombre de método o de propiedad del llamador.</span><span class="sxs-lookup"><span data-stu-id="f9534-116">Method name or property name of the caller.</span></span>|`String`|

<span data-ttu-id="f9534-117">Esta información facilita la creación de herramientas de seguimiento, depuración y diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="f9534-117">This information helps you write tracing, debugging, and create diagnostic tools.</span></span> <span data-ttu-id="f9534-118">En el ejemplo siguiente se muestra cómo usar atributos de información del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f9534-118">The following example shows how to use caller info attributes.</span></span> <span data-ttu-id="f9534-119">En cada llamada al método `TraceMessage`, la información del llamador se sustituye como argumentos para los parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="f9534-119">On each call to the `TraceMessage` method, the caller information is substituted as arguments to the optional parameters.</span></span>

```csharp
public void DoProcessing()
{
    TraceMessage("Something happened.");
}

public void TraceMessage(string message,
        [CallerMemberName] string memberName = "",
        [CallerFilePath] string sourceFilePath = "",
        [CallerLineNumber] int sourceLineNumber = 0)
{
    Trace.WriteLine("message: " + message);
    Trace.WriteLine("member name: " + memberName);
    Trace.WriteLine("source file path: " + sourceFilePath);
    Trace.WriteLine("source line number: " + sourceLineNumber);
}

// Sample Output:
//  message: Something happened.
//  member name: DoProcessing
//  source file path: c:\Visual Studio Projects\CallerInfoCS\CallerInfoCS\Form1.cs
//  source line number: 31
```

<span data-ttu-id="f9534-120">Debe especificar un valor predeterminado explícito para cada parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="f9534-120">You specify an explicit default value for each optional parameter.</span></span> <span data-ttu-id="f9534-121">No puede aplicar atributos de información del autor de la llamada a los parámetros que no se especifican como opcionales.</span><span class="sxs-lookup"><span data-stu-id="f9534-121">You can't apply caller info attributes to parameters that aren't specified as optional.</span></span> <span data-ttu-id="f9534-122">Los atributos de información del autor de la llamada no crean un parámetro opcional,</span><span class="sxs-lookup"><span data-stu-id="f9534-122">The caller info attributes don't make a parameter optional.</span></span> <span data-ttu-id="f9534-123">sino que influyen en el valor predeterminado que se pasa cuando se omite el argumento.</span><span class="sxs-lookup"><span data-stu-id="f9534-123">Instead, they affect the default value that's passed in when the argument is omitted.</span></span> <span data-ttu-id="f9534-124">Los valores de información del autor de la llamada se emiten como literales en el lenguaje intermedio (IL) en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="f9534-124">Caller info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="f9534-125">A diferencia de los resultados de la propiedad <xref:System.Exception.StackTrace%2A> para las excepciones, los resultados no se ven afectados por confusión.</span><span class="sxs-lookup"><span data-stu-id="f9534-125">Unlike the results of the <xref:System.Exception.StackTrace%2A> property for exceptions, the results aren't affected by obfuscation.</span></span> <span data-ttu-id="f9534-126">Puede proporcionar explícitamente los argumentos opcionales para controlar la información del llamador u ocultarla.</span><span class="sxs-lookup"><span data-stu-id="f9534-126">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

### <a name="member-names"></a><span data-ttu-id="f9534-127">Nombres de miembro</span><span class="sxs-lookup"><span data-stu-id="f9534-127">Member names</span></span>

<span data-ttu-id="f9534-128">Se puede utilizar el atributo `CallerMemberName` para evitar especificar el nombre de miembro como un argumento `String` para el método llamado.</span><span class="sxs-lookup"><span data-stu-id="f9534-128">You can use the `CallerMemberName` attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="f9534-129">Mediante esta técnica, se evita el problema de que la **refactorización de cambio de nombre** no cambie los valores `String`.</span><span class="sxs-lookup"><span data-stu-id="f9534-129">By using this technique, you avoid the problem that **Rename Refactoring** doesn't change the `String` values.</span></span> <span data-ttu-id="f9534-130">Esta ventaja es especialmente útil para las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="f9534-130">This benefit is especially useful for the following tasks:</span></span>

- <span data-ttu-id="f9534-131">Usar el seguimiento y las rutinas de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="f9534-131">Using tracing and diagnostic routines.</span></span>
- <span data-ttu-id="f9534-132">Implementar la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> al enlazar datos.</span><span class="sxs-lookup"><span data-stu-id="f9534-132">Implementing the <xref:System.ComponentModel.INotifyPropertyChanged> interface when binding data.</span></span> <span data-ttu-id="f9534-133">Esta interfaz permite que la propiedad de un objeto notifique a un control enlazado que la propiedad ha cambiado, de forma que el control pueda mostrar información actualizada.</span><span class="sxs-lookup"><span data-stu-id="f9534-133">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="f9534-134">Sin el atributo `CallerMemberName`, se debe especificar el nombre de propiedad como un literal.</span><span class="sxs-lookup"><span data-stu-id="f9534-134">Without the `CallerMemberName` attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="f9534-135">En el gráfico siguiente se muestran los nombres de miembro que se devuelven cuando se utiliza el atributo `CallerMemberName`.</span><span class="sxs-lookup"><span data-stu-id="f9534-135">The following chart shows the member names that are returned when you use the `CallerMemberName` attribute.</span></span>

|<span data-ttu-id="f9534-136">Las llamadas se producen en</span><span class="sxs-lookup"><span data-stu-id="f9534-136">Calls occur within</span></span>|<span data-ttu-id="f9534-137">Resultado del nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="f9534-137">Member name result</span></span>|
|-|-|
|<span data-ttu-id="f9534-138">Método, propiedad o evento</span><span class="sxs-lookup"><span data-stu-id="f9534-138">Method, property, or event</span></span>|<span data-ttu-id="f9534-139">Nombre del método, propiedad o evento en el que se originó la llamada.</span><span class="sxs-lookup"><span data-stu-id="f9534-139">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="f9534-140">Constructor</span><span class="sxs-lookup"><span data-stu-id="f9534-140">Constructor</span></span>|<span data-ttu-id="f9534-141">Cadena ".ctor"</span><span class="sxs-lookup"><span data-stu-id="f9534-141">The string ".ctor"</span></span>|
|<span data-ttu-id="f9534-142">Constructor estático</span><span class="sxs-lookup"><span data-stu-id="f9534-142">Static constructor</span></span>|<span data-ttu-id="f9534-143">Cadena ".cctor"</span><span class="sxs-lookup"><span data-stu-id="f9534-143">The string ".cctor"</span></span>|
|<span data-ttu-id="f9534-144">Destructor</span><span class="sxs-lookup"><span data-stu-id="f9534-144">Destructor</span></span>|<span data-ttu-id="f9534-145">Cadena "Finalize"</span><span class="sxs-lookup"><span data-stu-id="f9534-145">The string "Finalize"</span></span>|
|<span data-ttu-id="f9534-146">Conversiones u operadores definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="f9534-146">User-defined operators or conversions</span></span>|<span data-ttu-id="f9534-147">Nombre generado para el miembro, por ejemplo, "op_Addition".</span><span class="sxs-lookup"><span data-stu-id="f9534-147">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="f9534-148">Constructor de atributo</span><span class="sxs-lookup"><span data-stu-id="f9534-148">Attribute constructor</span></span>|<span data-ttu-id="f9534-149">Nombre del método o la propiedad a la que se aplica el atributo.</span><span class="sxs-lookup"><span data-stu-id="f9534-149">The name of the method or property to which the attribute is applied.</span></span> <span data-ttu-id="f9534-150">Si el atributo es cualquier elemento dentro de un miembro (como un parámetro, un valor devuelto o un parámetro de tipo genérico), el resultado es el nombre del miembro asociado a este elemento.</span><span class="sxs-lookup"><span data-stu-id="f9534-150">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="f9534-151">Ningún miembro contenedor (por ejemplo, nivel de ensamblado o atributos que se aplican a tipos)</span><span class="sxs-lookup"><span data-stu-id="f9534-151">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="f9534-152">El valor predeterminado del parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="f9534-152">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="f9534-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9534-153">See also</span></span>

- [<span data-ttu-id="f9534-154">Argumentos opcionales y con nombre</span><span class="sxs-lookup"><span data-stu-id="f9534-154">Named and Optional Arguments</span></span>](../../programming-guide/classes-and-structs/named-and-optional-arguments.md)
- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="f9534-155">Atributos</span><span class="sxs-lookup"><span data-stu-id="f9534-155">Attributes</span></span>](../../../standard/attributes/index.md)
