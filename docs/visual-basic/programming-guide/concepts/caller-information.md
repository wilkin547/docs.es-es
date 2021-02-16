---
description: 'Más información acerca de: información del autor de la llamada (Visual Basic)'
title: Información del llamador
ms.date: 07/20/2015
ms.assetid: 15d556eb-4d0c-4497-98a3-7f60abb7d6a1
ms.openlocfilehash: bcb4f553a9840a76f24825c3c2b7e2e98914abc2
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100437714"
---
# <a name="caller-information-visual-basic"></a><span data-ttu-id="22465-103">Información del llamador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22465-103">Caller Information (Visual Basic)</span></span>

<span data-ttu-id="22465-104">Mediante los atributos de información del llamador, se puede obtener información sobre el llamador de un método.</span><span class="sxs-lookup"><span data-stu-id="22465-104">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="22465-105">Puede obtener la ruta de acceso al código fuente, el número de línea en el código fuente y el nombre de miembro del llamador.</span><span class="sxs-lookup"><span data-stu-id="22465-105">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="22465-106">Esta información resulta útil para el seguimiento y la depuración, así como para crear herramientas de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="22465-106">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>  
  
 <span data-ttu-id="22465-107">Para obtener esta información, se usan los atributos que se aplican a los parámetros opcionales, que tienen valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="22465-107">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="22465-108">En la tabla siguiente se enumeran los atributos de información del llamador que se definen en el espacio de nombres <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="22465-108">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>  
  
|<span data-ttu-id="22465-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="22465-109">Attribute</span></span>|<span data-ttu-id="22465-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="22465-110">Description</span></span>|<span data-ttu-id="22465-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="22465-111">Type</span></span>|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="22465-112">Ruta de acceso completa del archivo de código fuente que contiene el llamador.</span><span class="sxs-lookup"><span data-stu-id="22465-112">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="22465-113">Esta es la ruta de acceso en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="22465-113">This is the file path at compile time.</span></span>|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="22465-114">Número de línea en el archivo de código fuente en el que se llama al método.</span><span class="sxs-lookup"><span data-stu-id="22465-114">Line number in the source file at which the method is called.</span></span>|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="22465-115">Método o nombre de propiedad del llamador.</span><span class="sxs-lookup"><span data-stu-id="22465-115">Method or property name of the caller.</span></span> <span data-ttu-id="22465-116">Vea [Nombres de miembro](#MEMBERNAMES) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="22465-116">See [Member Names](#MEMBERNAMES) later in this topic.</span></span>|`String`|  
  
## <a name="example"></a><span data-ttu-id="22465-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22465-117">Example</span></span>  

 <span data-ttu-id="22465-118">En el ejemplo siguiente se muestra cómo utilizar atributos de información del llamador.</span><span class="sxs-lookup"><span data-stu-id="22465-118">The following example shows how to use Caller Info attributes.</span></span> <span data-ttu-id="22465-119">En cada llamada al método `TraceMessage`, la información del llamador se sustituye como argumentos para los parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="22465-119">On each call to the `TraceMessage` method, the caller information is substituted as arguments to the optional parameters.</span></span>  
  
```vb  
Private Sub DoProcessing()  
    TraceMessage("Something happened.")  
End Sub  
  
Public Sub TraceMessage(message As String,  
        <System.Runtime.CompilerServices.CallerMemberName> Optional memberName As String = Nothing,  
        <System.Runtime.CompilerServices.CallerFilePath> Optional sourcefilePath As String = Nothing,  
        <System.Runtime.CompilerServices.CallerLineNumber()> Optional sourceLineNumber As Integer = 0)  
  
    System.Diagnostics.Trace.WriteLine("message: " & message)  
    System.Diagnostics.Trace.WriteLine("member name: " & memberName)  
    System.Diagnostics.Trace.WriteLine("source file path: " & sourcefilePath)  
    System.Diagnostics.Trace.WriteLine("source line number: " & sourceLineNumber)  
End Sub  
  
' Sample output:  
'   message: Something happened.  
'   member name: DoProcessing  
'   source file path: C:\Users\username\Documents\Visual Studio 2012\Projects\CallerInfoVB\CallerInfoVB\Form1.vb  
'   source line number: 15  
```  
  
## <a name="remarks"></a><span data-ttu-id="22465-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="22465-120">Remarks</span></span>  

 <span data-ttu-id="22465-121">Se debe especificar un valor predeterminado explícito para cada parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="22465-121">You must specify an explicit default value for each optional parameter.</span></span> <span data-ttu-id="22465-122">No se pueden aplicar atributos de información del llamador para los parámetros que no se especifican como opcionales.</span><span class="sxs-lookup"><span data-stu-id="22465-122">You can't apply Caller Info attributes to parameters that aren't specified as optional.</span></span>  
  
 <span data-ttu-id="22465-123">Los atributos de información del llamador no crean un parámetro opcional,</span><span class="sxs-lookup"><span data-stu-id="22465-123">The Caller Info attributes don't make a parameter optional.</span></span> <span data-ttu-id="22465-124">sino que influyen en el valor predeterminado que se pasa cuando se omite el argumento.</span><span class="sxs-lookup"><span data-stu-id="22465-124">Instead, they affect the default value that's passed in when the argument is omitted.</span></span>  
  
 <span data-ttu-id="22465-125">Los valores de información del llamador se emiten como literales en el lenguaje intermedio (IL) en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="22465-125">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="22465-126">A diferencia de los resultados de la propiedad <xref:System.Exception.StackTrace%2A> para las excepciones, los resultados no se ven afectados por confusión.</span><span class="sxs-lookup"><span data-stu-id="22465-126">Unlike the results of the <xref:System.Exception.StackTrace%2A> property for exceptions, the results aren't affected by obfuscation.</span></span>  
  
 <span data-ttu-id="22465-127">Puede proporcionar explícitamente los argumentos opcionales para controlar la información del llamador u ocultarla.</span><span class="sxs-lookup"><span data-stu-id="22465-127">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>  
  
### <a name="member-names"></a><a name="MEMBERNAMES"></a> <span data-ttu-id="22465-128">Nombres de miembro</span><span class="sxs-lookup"><span data-stu-id="22465-128">Member Names</span></span>  

 <span data-ttu-id="22465-129">Se puede utilizar el atributo `CallerMemberName` para evitar especificar el nombre de miembro como un argumento `String` para el método llamado.</span><span class="sxs-lookup"><span data-stu-id="22465-129">You can use the `CallerMemberName` attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="22465-130">Mediante esta técnica, se evita el problema de que la **refactorización de cambio de nombre** no cambie los valores `String`.</span><span class="sxs-lookup"><span data-stu-id="22465-130">By using this technique, you avoid the problem that **Rename Refactoring** doesn't change the `String` values.</span></span> <span data-ttu-id="22465-131">Esta ventaja es especialmente útil para las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="22465-131">This benefit is especially useful for the following tasks:</span></span>  
  
- <span data-ttu-id="22465-132">Usar el seguimiento y las rutinas de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="22465-132">Using tracing and diagnostic routines.</span></span>  
  
- <span data-ttu-id="22465-133">Implementar la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> al enlazar datos.</span><span class="sxs-lookup"><span data-stu-id="22465-133">Implementing the <xref:System.ComponentModel.INotifyPropertyChanged> interface when binding data.</span></span> <span data-ttu-id="22465-134">Esta interfaz permite que la propiedad de un objeto notifique a un control enlazado que la propiedad ha cambiado, de forma que el control pueda mostrar información actualizada.</span><span class="sxs-lookup"><span data-stu-id="22465-134">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="22465-135">Sin el atributo `CallerMemberName`, se debe especificar el nombre de propiedad como un literal.</span><span class="sxs-lookup"><span data-stu-id="22465-135">Without the `CallerMemberName` attribute, you must specify the property name as a literal.</span></span>  
  
 <span data-ttu-id="22465-136">En el gráfico siguiente se muestran los nombres de miembro que se devuelven cuando se utiliza el atributo `CallerMemberName`.</span><span class="sxs-lookup"><span data-stu-id="22465-136">The following chart shows the member names that are returned when you use the `CallerMemberName` attribute.</span></span>  
  
|<span data-ttu-id="22465-137">Las llamadas se producen en</span><span class="sxs-lookup"><span data-stu-id="22465-137">Calls occurs within</span></span>|<span data-ttu-id="22465-138">Resultado del nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="22465-138">Member name result</span></span>|  
|-------------------------|------------------------|  
|<span data-ttu-id="22465-139">Método, propiedad o evento</span><span class="sxs-lookup"><span data-stu-id="22465-139">Method, property, or event</span></span>|<span data-ttu-id="22465-140">Nombre del método, propiedad o evento en el que se originó la llamada.</span><span class="sxs-lookup"><span data-stu-id="22465-140">The name of the method, property, or event from which the call originated.</span></span>|  
|<span data-ttu-id="22465-141">Constructor</span><span class="sxs-lookup"><span data-stu-id="22465-141">Constructor</span></span>|<span data-ttu-id="22465-142">Cadena ".ctor"</span><span class="sxs-lookup"><span data-stu-id="22465-142">The string ".ctor"</span></span>|  
|<span data-ttu-id="22465-143">Constructor estático</span><span class="sxs-lookup"><span data-stu-id="22465-143">Static constructor</span></span>|<span data-ttu-id="22465-144">Cadena ".cctor"</span><span class="sxs-lookup"><span data-stu-id="22465-144">The string ".cctor"</span></span>|  
|<span data-ttu-id="22465-145">Destructor</span><span class="sxs-lookup"><span data-stu-id="22465-145">Destructor</span></span>|<span data-ttu-id="22465-146">Cadena "Finalize"</span><span class="sxs-lookup"><span data-stu-id="22465-146">The string "Finalize"</span></span>|  
|<span data-ttu-id="22465-147">Conversiones u operadores definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="22465-147">User-defined operators or conversions</span></span>|<span data-ttu-id="22465-148">Nombre generado para el miembro, por ejemplo, "op_Addition".</span><span class="sxs-lookup"><span data-stu-id="22465-148">The generated name for the member, for example, "op_Addition".</span></span>|  
|<span data-ttu-id="22465-149">Constructor de atributo</span><span class="sxs-lookup"><span data-stu-id="22465-149">Attribute constructor</span></span>|<span data-ttu-id="22465-150">Nombre del miembro al que se aplica el atributo.</span><span class="sxs-lookup"><span data-stu-id="22465-150">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="22465-151">Si el atributo es cualquier elemento dentro de un miembro (como un parámetro, un valor devuelto o un parámetro de tipo genérico), el resultado es el nombre del miembro asociado a este elemento.</span><span class="sxs-lookup"><span data-stu-id="22465-151">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|  
|<span data-ttu-id="22465-152">Ningún miembro contenedor (por ejemplo, nivel de ensamblado o atributos que se aplican a tipos)</span><span class="sxs-lookup"><span data-stu-id="22465-152">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="22465-153">El valor predeterminado del parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="22465-153">The default value of the optional parameter.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="22465-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="22465-154">See also</span></span>

- [<span data-ttu-id="22465-155">Atributos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="22465-155">Attributes (Visual Basic)</span></span>](../../language-reference/attributes.md)
- <span data-ttu-id="22465-156">[Common Attributes (Visual Basic)](attributes/common-attributes.md) (Atributos comunes [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="22465-156">[Common Attributes (Visual Basic)](attributes/common-attributes.md)</span></span>
- [<span data-ttu-id="22465-157">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="22465-157">Optional Parameters</span></span>](../language-features/procedures/optional-parameters.md)
- [<span data-ttu-id="22465-158">Conceptos de programación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22465-158">Programming Concepts (Visual Basic)</span></span>](index.md)
