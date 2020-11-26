---
title: Mejorar la depuración con los atributos de visualización del depurador
description: Introducción a los atributos de presentación del depurador en .NET, que permiten al desarrollador de tipos especificar también el aspecto que tendrá el tipo cuando se muestre en un depurador.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- debugger, display attributes
- DebuggerTypeProxyAttribute attribute
- debugging [.NET Framework], debugger display attributes
- DebuggerDisplayAttribute attribute
- display attributes for debugger
- DebuggerBrowsableAttribute attribute
ms.assetid: 72bb7aa9-459b-42c4-9163-9312fab4c410
ms.openlocfilehash: 2e556358490409a0fa7b345c4454eb43cf607e32
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244371"
---
# <a name="enhancing-debugging-with-the-debugger-display-attributes"></a><span data-ttu-id="f7ffb-103">Mejorar la depuración con los atributos de visualización del depurador</span><span class="sxs-lookup"><span data-stu-id="f7ffb-103">Enhancing Debugging with the Debugger Display Attributes</span></span>

<span data-ttu-id="f7ffb-104">Los atributos de visualización del depurador permiten al desarrollador del tipo, que especifica y mejor comprende el comportamiento del runtime de ese tipo, que especifique también el aspecto que tendrá ese tipo cuando se muestre en un depurador.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-104">Debugger display attributes allow the developer of the type, who specifies and best understands the runtime behavior of that type, to also specify what that type will look like when it is displayed in a debugger.</span></span> <span data-ttu-id="f7ffb-105">Además, los atributos de visualización del depurador que proporcionan una propiedad `Target` pueden aplicarse en el nivel de ensamblado por usuarios sin conocimiento del código fuente.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-105">In addition, debugger display attributes that provide a `Target` property can be applied at the assembly level by users without knowledge of the source code.</span></span> <span data-ttu-id="f7ffb-106">El atributo <xref:System.Diagnostics.DebuggerDisplayAttribute> controla la forma en que se muestra un tipo o un miembro en las ventanas de variables del depurador.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-106">The <xref:System.Diagnostics.DebuggerDisplayAttribute> attribute controls how a type or member is displayed in the debugger variable windows.</span></span> <span data-ttu-id="f7ffb-107">El atributo <xref:System.Diagnostics.DebuggerBrowsableAttribute> determina si un campo o propiedad se muestra en las ventanas de variables del depurador y cómo se muestra.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-107">The <xref:System.Diagnostics.DebuggerBrowsableAttribute> attribute determines if and how a field or property is displayed in the debugger variable windows.</span></span> <span data-ttu-id="f7ffb-108">El atributo <xref:System.Diagnostics.DebuggerTypeProxyAttribute> especifica un tipo sustitutivo, o un proxy, para un tipo y cambia la forma en que se muestra el tipo en las ventanas del depurador.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-108">The <xref:System.Diagnostics.DebuggerTypeProxyAttribute> attribute specifies a substitute type, or a proxy, for a type and changes the way the type is displayed in debugger windows.</span></span> <span data-ttu-id="f7ffb-109">Cuando se ve una variable que tiene un proxy, o un tipo sustitutivo, el proxy reemplaza al tipo original en la ventana de presentación del depurador.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-109">When you view a variable that has a proxy, or substitute type, the proxy stands in for the original type in the debugger display window.</span></span> <span data-ttu-id="f7ffb-110">En la ventana de las variables del depurador se muestran sólo los miembros públicos del tipo de servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-110">The debugger variable window displays only the public members of the proxy type.</span></span> <span data-ttu-id="f7ffb-111">No se muestran los miembros privados.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-111">Private members are not displayed.</span></span>  
  
## <a name="using-the-debuggerdisplayattribute"></a><span data-ttu-id="f7ffb-112">Usar el atributo DebuggerDisplayAttribute</span><span class="sxs-lookup"><span data-stu-id="f7ffb-112">Using the DebuggerDisplayAttribute</span></span>  

<span data-ttu-id="f7ffb-113">El constructor <xref:System.Diagnostics.DebuggerDisplayAttribute.%23ctor%2A> tiene un argumento único: una cadena que se va a mostrar en la columna de valor de las instancias del tipo.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-113">The <xref:System.Diagnostics.DebuggerDisplayAttribute.%23ctor%2A> constructor has a single argument: a string to be displayed in the value column for instances of the type.</span></span> <span data-ttu-id="f7ffb-114">Esta cadena puede contener llaves ({ y }).</span><span class="sxs-lookup"><span data-stu-id="f7ffb-114">This string can contain braces ({ and }).</span></span> <span data-ttu-id="f7ffb-115">El texto encerrado entre llaves se evalúa como una expresión.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-115">The text within a pair of braces is evaluated as an expression.</span></span> <span data-ttu-id="f7ffb-116">Por ejemplo, el código de C# siguiente hace que "Recuento = 4" se muestre cuando el signo más (+) está seleccionado para expandir la presentación del depurador para una instancia de `MyHashtable`.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-116">For example, the following C# code causes "Count = 4" to be displayed when the plus sign (+) is selected to expand the debugger display for an instance of `MyHashtable`.</span></span>  

```csharp
[DebuggerDisplay("Count = {count}")]
class MyHashtable
{
    public int count = 4;
}
```

<span data-ttu-id="f7ffb-117">Los atributos que se aplican en las propiedades a las que se hace referencia en la expresión no se procesan.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-117">Attributes applied to properties referenced in the expression are not processed.</span></span> <span data-ttu-id="f7ffb-118">Para el compilador de C#, se permite una expresión general que solo tenga acceso implícito a esta referencia para la instancia actual del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-118">For the C# compiler, a general expression is allowed that has only implicit access to this reference for the current instance of the target type.</span></span> <span data-ttu-id="f7ffb-119">La expresión está limitada; no tiene acceso a los alias, variables locales ni punteros.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-119">The expression is limited; there is no access to aliases, locals, or pointers.</span></span> <span data-ttu-id="f7ffb-120">En el código de C#, puede usar una expresión general entre las llaves que tenga acceso implícito al puntero `this` solo para la instancia actual del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-120">In C# code, you can use a general expression between the braces that has implicit access to the `this` pointer for the current instance of the target type only.</span></span>

<span data-ttu-id="f7ffb-121">Por ejemplo, si un objeto de C# tiene un `ToString()` invalidado, el depurador llamará a la invalidación y mostrará su resultado en lugar del `{<typeName>}.` estándar. Por lo tanto, si ha invalidado `ToString()`, no necesita usar <xref:System.Diagnostics.DebuggerDisplayAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-121">For example, if a C# object has an overridden `ToString()`, the debugger will call the override and show its result instead of the standard `{<typeName>}.` Thus, if you have overridden `ToString()`, you do not need to use <xref:System.Diagnostics.DebuggerDisplayAttribute>.</span></span> <span data-ttu-id="f7ffb-122">Si utiliza ambos, el atributo <xref:System.Diagnostics.DebuggerDisplayAttribute> tiene prioridad sobre el reemplazo de `ToString()`.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-122">If you use both, the <xref:System.Diagnostics.DebuggerDisplayAttribute> attribute takes precedence over the `ToString()` override.</span></span>

## <a name="using-the-debuggerbrowsableattribute"></a><span data-ttu-id="f7ffb-123">Usar el atributo DebuggerBrowsableAttribute</span><span class="sxs-lookup"><span data-stu-id="f7ffb-123">Using the DebuggerBrowsableAttribute</span></span>

 <span data-ttu-id="f7ffb-124">Aplique <xref:System.Diagnostics.DebuggerBrowsableAttribute> en un campo o propiedad para especificar cómo va a mostrarse el campo o la propiedad en la ventana del depurador.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-124">Apply the <xref:System.Diagnostics.DebuggerBrowsableAttribute> to a field or property to specify how the field or property is to be displayed in the debugger window.</span></span> <span data-ttu-id="f7ffb-125">El constructor de este atributo toma uno de los valores de enumeración <xref:System.Diagnostics.DebuggerBrowsableState>, que especifica uno de los estados siguientes:</span><span class="sxs-lookup"><span data-stu-id="f7ffb-125">The constructor for this attribute takes one of the <xref:System.Diagnostics.DebuggerBrowsableState> enumeration values, which specifies one of the following states:</span></span>

- <span data-ttu-id="f7ffb-126"><xref:System.Diagnostics.DebuggerBrowsableState.Never> indica que el miembro no se muestra en la ventana de datos.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-126"><xref:System.Diagnostics.DebuggerBrowsableState.Never> indicates that the member is not displayed in the data window.</span></span>  <span data-ttu-id="f7ffb-127">Por ejemplo, con este valor para <xref:System.Diagnostics.DebuggerBrowsableAttribute> en un campo se quita el campo de la jerarquía; el campo no se muestra cuando expande el tipo envolvente haciendo clic en el signo más (+) para la instancia del tipo.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-127">For example, using this value for the <xref:System.Diagnostics.DebuggerBrowsableAttribute> on a field removes the field from the hierarchy; the field is not displayed when you expand the enclosing type by clicking the plus sign (+) for the type instance.</span></span>

- <span data-ttu-id="f7ffb-128"><xref:System.Diagnostics.DebuggerBrowsableState.Collapsed> indica que el miembro se muestra pero no se expande de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-128"><xref:System.Diagnostics.DebuggerBrowsableState.Collapsed> indicates that the member is displayed but not expanded by default.</span></span>  <span data-ttu-id="f7ffb-129">Este es el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-129">This is the default behavior.</span></span>

- <span data-ttu-id="f7ffb-130"><xref:System.Diagnostics.DebuggerBrowsableState.RootHidden> indica que el propio miembro no se muestra, pero sus objetos constituyentes se muestran si es una matriz o una colección.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-130"><xref:System.Diagnostics.DebuggerBrowsableState.RootHidden> indicates that the member itself is not shown, but its constituent objects are displayed if it is an array or collection.</span></span>

> [!NOTE]
> <span data-ttu-id="f7ffb-131"><xref:System.Diagnostics.DebuggerBrowsableAttribute> no es compatible con Visual Basic en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-131">The <xref:System.Diagnostics.DebuggerBrowsableAttribute> is not supported by Visual Basic in the .NET Framework version 2.0.</span></span>

<span data-ttu-id="f7ffb-132">En el siguiente ejemplo de código se muestra el uso de <xref:System.Diagnostics.DebuggerBrowsableAttribute> para evitar que la propiedad que lo sigue aparezca en la ventana del depurador para la clase.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-132">The following code example shows the use of the <xref:System.Diagnostics.DebuggerBrowsableAttribute> to prevent the property following it from appearing in the debug window for the class.</span></span>

```csharp
[DebuggerBrowsable(DebuggerBrowsableState.Never)]
public static string y = "Test String";
```

## <a name="using-the-debuggertypeproxy"></a><span data-ttu-id="f7ffb-133">Usar DebuggerTypeProxy</span><span class="sxs-lookup"><span data-stu-id="f7ffb-133">Using the DebuggerTypeProxy</span></span>

 <span data-ttu-id="f7ffb-134">Use el atributo <xref:System.Diagnostics.DebuggerTypeProxyAttribute> cuando necesite realizar cambios significativos y fundamentales en la vista de depuración de un tipo, sin cambiar el propio tipo.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-134">Use the <xref:System.Diagnostics.DebuggerTypeProxyAttribute> attribute when you need to significantly and fundamentally change the debugging view of a type, but not change the type itself.</span></span> <span data-ttu-id="f7ffb-135">El atributo <xref:System.Diagnostics.DebuggerTypeProxyAttribute> se usa para especificar un servidor proxy de presentación de un tipo y permitir a un desarrollador que ajuste la vista para el tipo.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-135">The <xref:System.Diagnostics.DebuggerTypeProxyAttribute> attribute is used to specify a display proxy for a type, allowing a developer to tailor the view for the type.</span></span>  <span data-ttu-id="f7ffb-136">Este atributo, como <xref:System.Diagnostics.DebuggerDisplayAttribute>, también se puede usar en el nivel de ensamblado, en cuyo caso la propiedad <xref:System.Diagnostics.DebuggerTypeProxyAttribute.Target%2A> especifica el tipo para el que se usará el servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-136">This attribute, like the <xref:System.Diagnostics.DebuggerDisplayAttribute>, can be used at the assembly level, in which case the <xref:System.Diagnostics.DebuggerTypeProxyAttribute.Target%2A> property specifies the type for which the proxy will be used.</span></span> <span data-ttu-id="f7ffb-137">El uso recomendado es que este atributo especifique un tipo anidado privado que aparece dentro del tipo al que se aplica el atributo.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-137">The recommended usage is that this attribute specifies a private nested type that occurs within the type to which the attribute is applied.</span></span>  <span data-ttu-id="f7ffb-138">Un evaluador de expresiones que admite los visores de tipo comprueba la existencia de este atributo cuando se muestra un tipo.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-138">An expression evaluator that supports type viewers checks for this attribute when a type is displayed.</span></span> <span data-ttu-id="f7ffb-139">Si se encuentra el atributo, el evaluador de expresiones sustituye el tipo de servidor proxy de presentación por el tipo al que se aplica el atributo.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-139">If the attribute is found, the expression evaluator substitutes the display proxy type for the type the attribute is applied to.</span></span>

 <span data-ttu-id="f7ffb-140">Cuando está presente <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, en la ventana de las variables del depurador se muestran solo los miembros públicos del tipo de servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-140">When the <xref:System.Diagnostics.DebuggerTypeProxyAttribute> is present, the debugger variable window displays only the public members of the proxy type.</span></span> <span data-ttu-id="f7ffb-141">No se muestran los miembros privados.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-141">Private members are not displayed.</span></span> <span data-ttu-id="f7ffb-142">El comportamiento de la ventana de datos no lo modifican las vistas mejoradas por atributos.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-142">The behavior of the data window is not changed by attribute-enhanced views.</span></span>

 <span data-ttu-id="f7ffb-143">Para evitar disminuciones innecesarias del rendimiento, los atributos del servidor proxy de presentación no se procesan hasta que el objeto esté expandido, ya sea a través del usuario que hace clic en el signo más (+) situado junto al tipo en una ventana de datos o a través de la aplicación del atributo <xref:System.Diagnostics.DebuggerBrowsableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-143">To avoid unnecessary performance penalties, attributes of the display proxy are not processed until the object is expanded, either through the user clicking the plus sign (+) next to the type in a data window, or through the application of the <xref:System.Diagnostics.DebuggerBrowsableAttribute> attribute.</span></span> <span data-ttu-id="f7ffb-144">Por consiguiente, se recomienda no aplicar ningún atributo al tipo de presentación.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-144">Therefore, it is recommended that no attributes be applied to the display type.</span></span> <span data-ttu-id="f7ffb-145">Los atributos pueden y deben aplicarse en el cuerpo del tipo de presentación.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-145">Attributes can and should be applied within the body of the display type.</span></span>

 <span data-ttu-id="f7ffb-146">En el ejemplo de código siguiente se muestra el uso del atributo <xref:System.Diagnostics.DebuggerTypeProxyAttribute> para especificar un tipo que se va a usar como servidor proxy de presentación del depurador.</span><span class="sxs-lookup"><span data-stu-id="f7ffb-146">The following code example shows the use of the <xref:System.Diagnostics.DebuggerTypeProxyAttribute> to specify a type to be used as a debugger display proxy.</span></span>

```csharp
[DebuggerTypeProxy(typeof(HashtableDebugView))]
class MyHashtable : Hashtable
{
    private const string TestString =
        "This should not appear in the debug window.";

    internal class HashtableDebugView
    {
        private Hashtable hashtable;
        public const string TestStringProxy =
            "This should appear in the debug window.";

        // The constructor for the type proxy class must have a
        // constructor that takes the target type as a parameter.
        public HashtableDebugView(Hashtable hashtable)
        {
            this.hashtable = hashtable;
        }
    }
}
```

## <a name="example"></a><span data-ttu-id="f7ffb-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f7ffb-147">Example</span></span>

### <a name="description"></a><span data-ttu-id="f7ffb-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7ffb-148">Description</span></span>

<span data-ttu-id="f7ffb-149">El siguiente ejemplo de código se puede ver en Visual Studio para ver los resultados de aplicar <xref:System.Diagnostics.DebuggerDisplayAttribute> los <xref:System.Diagnostics.DebuggerBrowsableAttribute> atributos, y <xref:System.Diagnostics.DebuggerTypeProxyAttribute> .</span><span class="sxs-lookup"><span data-stu-id="f7ffb-149">The following code example can be viewed in Visual Studio to see the results of applying the <xref:System.Diagnostics.DebuggerDisplayAttribute>, <xref:System.Diagnostics.DebuggerBrowsableAttribute>, and <xref:System.Diagnostics.DebuggerTypeProxyAttribute> attributes.</span></span>

### <a name="code"></a><span data-ttu-id="f7ffb-150">Código</span><span class="sxs-lookup"><span data-stu-id="f7ffb-150">Code</span></span>

[!code-cpp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/cpp/program.cpp#1)]
[!code-csharp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/CS/program.cs#1)]
[!code-vb[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/VB/module1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="f7ffb-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f7ffb-151">See also</span></span>

- <xref:System.Diagnostics.DebuggerDisplayAttribute>
- <xref:System.Diagnostics.DebuggerBrowsableAttribute>
- <xref:System.Diagnostics.DebuggerTypeProxyAttribute>
