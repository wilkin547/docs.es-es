---
title: Información del llamador (C#)
ms.date: 07/20/2015
ms.assetid: ffad3d24-2fb7-4641-9124-53b5bc91d339
ms.openlocfilehash: 048e91ad337f74ef04a2a03412a44a0be0ef9506
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44212456"
---
# <a name="caller-information-c"></a><span data-ttu-id="50f98-102">Información del llamador (C#)</span><span class="sxs-lookup"><span data-stu-id="50f98-102">Caller Information (C#)</span></span>
<span data-ttu-id="50f98-103">Mediante los atributos de información del llamador, se puede obtener información sobre el llamador de un método.</span><span class="sxs-lookup"><span data-stu-id="50f98-103">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="50f98-104">Puede obtener la ruta de acceso al código fuente, el número de línea en el código fuente y el nombre de miembro del llamador.</span><span class="sxs-lookup"><span data-stu-id="50f98-104">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="50f98-105">Esta información resulta útil para el seguimiento y la depuración, así como para crear herramientas de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="50f98-105">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>  
  
 <span data-ttu-id="50f98-106">Para obtener esta información, se usan los atributos que se aplican a los parámetros opcionales, que tienen valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="50f98-106">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="50f98-107">En la tabla siguiente se enumeran los atributos de información del llamador que se definen en el espacio de nombres <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="50f98-107">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>  
  
|<span data-ttu-id="50f98-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="50f98-108">Attribute</span></span>|<span data-ttu-id="50f98-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="50f98-109">Description</span></span>|<span data-ttu-id="50f98-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="50f98-110">Type</span></span>|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="50f98-111">Ruta de acceso completa del archivo de código fuente que contiene el llamador.</span><span class="sxs-lookup"><span data-stu-id="50f98-111">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="50f98-112">Esta es la ruta de acceso en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="50f98-112">This is the file path at compile time.</span></span>|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="50f98-113">Número de línea en el archivo de código fuente en el que se llama al método.</span><span class="sxs-lookup"><span data-stu-id="50f98-113">Line number in the source file at which the method is called.</span></span>|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="50f98-114">Método o nombre de propiedad del llamador.</span><span class="sxs-lookup"><span data-stu-id="50f98-114">Method or property name of the caller.</span></span> <span data-ttu-id="50f98-115">Vea [Nombres de miembro](#MEMBERNAMES) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="50f98-115">See [Member Names](#MEMBERNAMES) later in this topic.</span></span>|`String`|  
  
## <a name="example"></a><span data-ttu-id="50f98-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="50f98-116">Example</span></span>  
 <span data-ttu-id="50f98-117">En el ejemplo siguiente se muestra cómo utilizar atributos de información del llamador.</span><span class="sxs-lookup"><span data-stu-id="50f98-117">The following example shows how to use Caller Info attributes.</span></span> <span data-ttu-id="50f98-118">En cada llamada al método `TraceMessage`, la información del llamador se sustituye como argumentos para los parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="50f98-118">On each call to the `TraceMessage` method, the caller information is substituted as arguments to the optional parameters.</span></span>  
  
```csharp  
public void DoProcessing()  
{  
    TraceMessage("Something happened.");  
}  
  
public void TraceMessage(string message,  
        [System.Runtime.CompilerServices.CallerMemberName] string memberName = "",  
        [System.Runtime.CompilerServices.CallerFilePath] string sourceFilePath = "",  
        [System.Runtime.CompilerServices.CallerLineNumber] int sourceLineNumber = 0)  
{  
    System.Diagnostics.Trace.WriteLine("message: " + message);  
    System.Diagnostics.Trace.WriteLine("member name: " + memberName);  
    System.Diagnostics.Trace.WriteLine("source file path: " + sourceFilePath);  
    System.Diagnostics.Trace.WriteLine("source line number: " + sourceLineNumber);  
}  
  
// Sample Output:  
//  message: Something happened.  
//  member name: DoProcessing  
//  source file path: c:\Users\username\Documents\Visual Studio 2012\Projects\CallerInfoCS\CallerInfoCS\Form1.cs  
//  source line number: 31  
```  
  
## <a name="remarks"></a><span data-ttu-id="50f98-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="50f98-119">Remarks</span></span>  
 <span data-ttu-id="50f98-120">Se debe especificar un valor predeterminado explícito para cada parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="50f98-120">You must specify an explicit default value for each optional parameter.</span></span> <span data-ttu-id="50f98-121">No se pueden aplicar atributos de información del llamador para los parámetros que no se especifican como opcionales.</span><span class="sxs-lookup"><span data-stu-id="50f98-121">You can't apply Caller Info attributes to parameters that aren't specified as optional.</span></span>  
  
 <span data-ttu-id="50f98-122">Los atributos de información del llamador no crean un parámetro opcional,</span><span class="sxs-lookup"><span data-stu-id="50f98-122">The Caller Info attributes don't make a parameter optional.</span></span> <span data-ttu-id="50f98-123">sino que influyen en el valor predeterminado que se pasa cuando se omite el argumento.</span><span class="sxs-lookup"><span data-stu-id="50f98-123">Instead, they affect the default value that's passed in when the argument is omitted.</span></span>  
  
 <span data-ttu-id="50f98-124">Los valores de información del llamador se emiten como literales en el lenguaje intermedio (IL) en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="50f98-124">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="50f98-125">A diferencia de los resultados de la propiedad <xref:System.Exception.StackTrace%2A> para las excepciones, los resultados no se ven afectados por confusión.</span><span class="sxs-lookup"><span data-stu-id="50f98-125">Unlike the results of the <xref:System.Exception.StackTrace%2A> property for exceptions, the results aren't affected by obfuscation.</span></span>  
  
 <span data-ttu-id="50f98-126">Puede proporcionar explícitamente los argumentos opcionales para controlar la información del llamador u ocultarla.</span><span class="sxs-lookup"><span data-stu-id="50f98-126">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>  
  
###  <a name="MEMBERNAMES"></a> <span data-ttu-id="50f98-127">Nombres de miembro</span><span class="sxs-lookup"><span data-stu-id="50f98-127">Member Names</span></span>  
 <span data-ttu-id="50f98-128">Se puede utilizar el atributo `CallerMemberName` para evitar especificar el nombre de miembro como un argumento `String` para el método llamado.</span><span class="sxs-lookup"><span data-stu-id="50f98-128">You can use the `CallerMemberName` attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="50f98-129">Mediante esta técnica, se evita el problema de que la **refactorización de cambio de nombre** no cambie los valores `String`.</span><span class="sxs-lookup"><span data-stu-id="50f98-129">By using this technique, you avoid the problem that **Rename Refactoring** doesn't change the `String` values.</span></span> <span data-ttu-id="50f98-130">Esta ventaja es especialmente útil para las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="50f98-130">This benefit is especially useful for the following tasks:</span></span>  
  
-   <span data-ttu-id="50f98-131">Usar el seguimiento y las rutinas de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="50f98-131">Using tracing and diagnostic routines.</span></span>  
  
-   <span data-ttu-id="50f98-132">Implementar la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> al enlazar datos.</span><span class="sxs-lookup"><span data-stu-id="50f98-132">Implementing the <xref:System.ComponentModel.INotifyPropertyChanged> interface when binding data.</span></span> <span data-ttu-id="50f98-133">Esta interfaz permite que la propiedad de un objeto notifique a un control enlazado que la propiedad ha cambiado, de forma que el control pueda mostrar información actualizada.</span><span class="sxs-lookup"><span data-stu-id="50f98-133">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="50f98-134">Sin el atributo `CallerMemberName`, se debe especificar el nombre de propiedad como un literal.</span><span class="sxs-lookup"><span data-stu-id="50f98-134">Without the `CallerMemberName` attribute, you must specify the property name as a literal.</span></span>  
  
 <span data-ttu-id="50f98-135">En el gráfico siguiente se muestran los nombres de miembro que se devuelven cuando se utiliza el atributo `CallerMemberName`.</span><span class="sxs-lookup"><span data-stu-id="50f98-135">The following chart shows the member names that are returned when you use the `CallerMemberName` attribute.</span></span>  
  
|<span data-ttu-id="50f98-136">Las llamadas se producen en</span><span class="sxs-lookup"><span data-stu-id="50f98-136">Calls occurs within</span></span>|<span data-ttu-id="50f98-137">Resultado del nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="50f98-137">Member name result</span></span>|  
|-------------------------|------------------------|  
|<span data-ttu-id="50f98-138">Método, propiedad o evento</span><span class="sxs-lookup"><span data-stu-id="50f98-138">Method, property, or event</span></span>|<span data-ttu-id="50f98-139">Nombre del método, propiedad o evento en el que se originó la llamada.</span><span class="sxs-lookup"><span data-stu-id="50f98-139">The name of the method, property, or event from which the call originated.</span></span>|  
|<span data-ttu-id="50f98-140">Constructor</span><span class="sxs-lookup"><span data-stu-id="50f98-140">Constructor</span></span>|<span data-ttu-id="50f98-141">Cadena ".ctor"</span><span class="sxs-lookup"><span data-stu-id="50f98-141">The string ".ctor"</span></span>|  
|<span data-ttu-id="50f98-142">Constructor estático</span><span class="sxs-lookup"><span data-stu-id="50f98-142">Static constructor</span></span>|<span data-ttu-id="50f98-143">Cadena ".cctor"</span><span class="sxs-lookup"><span data-stu-id="50f98-143">The string ".cctor"</span></span>|  
|<span data-ttu-id="50f98-144">Destructor</span><span class="sxs-lookup"><span data-stu-id="50f98-144">Destructor</span></span>|<span data-ttu-id="50f98-145">Cadena "Finalize"</span><span class="sxs-lookup"><span data-stu-id="50f98-145">The string "Finalize"</span></span>|  
|<span data-ttu-id="50f98-146">Conversiones u operadores definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="50f98-146">User-defined operators or conversions</span></span>|<span data-ttu-id="50f98-147">Nombre generado para el miembro, por ejemplo, "op_Addition".</span><span class="sxs-lookup"><span data-stu-id="50f98-147">The generated name for the member, for example, "op_Addition".</span></span>|  
|<span data-ttu-id="50f98-148">Constructor de atributo</span><span class="sxs-lookup"><span data-stu-id="50f98-148">Attribute constructor</span></span>|<span data-ttu-id="50f98-149">Nombre del miembro al que se aplica el atributo.</span><span class="sxs-lookup"><span data-stu-id="50f98-149">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="50f98-150">Si el atributo es cualquier elemento dentro de un miembro (como un parámetro, un valor devuelto o un parámetro de tipo genérico), el resultado es el nombre del miembro asociado a este elemento.</span><span class="sxs-lookup"><span data-stu-id="50f98-150">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|  
|<span data-ttu-id="50f98-151">Ningún miembro contenedor (por ejemplo, nivel de ensamblado o atributos que se aplican a tipos)</span><span class="sxs-lookup"><span data-stu-id="50f98-151">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="50f98-152">El valor predeterminado del parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="50f98-152">The default value of the optional parameter.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="50f98-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="50f98-153">See Also</span></span>

- [<span data-ttu-id="50f98-154">Atributos (C#)</span><span class="sxs-lookup"><span data-stu-id="50f98-154">Attributes (C#)</span></span>](../../../csharp/programming-guide/concepts/attributes/index.md)  
- [<span data-ttu-id="50f98-155">Atributos comunes (C#)</span><span class="sxs-lookup"><span data-stu-id="50f98-155">Common Attributes (C#)</span></span>](../../../csharp/programming-guide/concepts/attributes/common-attributes.md)  
- [<span data-ttu-id="50f98-156">Argumentos opcionales y con nombre</span><span class="sxs-lookup"><span data-stu-id="50f98-156">Named and Optional Arguments</span></span>](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)  
- [<span data-ttu-id="50f98-157">Conceptos de programación (C#)</span><span class="sxs-lookup"><span data-stu-id="50f98-157">Programming Concepts (C#)</span></span>](../../../csharp/programming-guide/concepts/index.md)
