---
title: Propiedades de dependencia
ms.date: 10/22/2008
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
ms.openlocfilehash: c6cebd7c6c630af6a1a439b48faccad2aea74a91
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821377"
---
# <a name="dependency-properties"></a><span data-ttu-id="f510f-102">Propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="f510f-102">Dependency Properties</span></span>
<span data-ttu-id="f510f-103">Una propiedad de dependencia (DP) es una propiedad normal que almacena su valor en un almacén de propiedades en lugar de almacenarlo en una variable de tipo (campo), por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f510f-103">A dependency property (DP) is a regular property that stores its value in a property store instead of storing it in a type variable (field), for example.</span></span>

 <span data-ttu-id="f510f-104">Una propiedad de dependencia asociada es un tipo de propiedad de dependencia modelada como métodos estáticos get y set que representan "propiedades" que describen las relaciones entre los objetos y sus contenedores (por ejemplo, la posición de un `Button` objeto en un `Panel` contenedor).</span><span class="sxs-lookup"><span data-stu-id="f510f-104">An attached dependency property is a kind of dependency property modeled as static Get and Set methods representing "properties" describing relationships between objects and their containers (e.g., the position of a `Button` object on a `Panel` container).</span></span>

 <span data-ttu-id="f510f-105">✔️ proporcionan las propiedades de dependencia, si necesita que las propiedades admitan características de WPF como el estilo, los desencadenadores, el enlace de datos, las animaciones, los recursos dinámicos y la herencia.</span><span class="sxs-lookup"><span data-stu-id="f510f-105">✔️ DO provide the dependency properties, if you need the properties to support WPF features such as styling, triggers, data binding, animations, dynamic resources, and inheritance.</span></span>

## <a name="dependency-property-design"></a><span data-ttu-id="f510f-106">Diseño de propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="f510f-106">Dependency Property Design</span></span>
 <span data-ttu-id="f510f-107">✔️ heredan de <xref:System.Windows.DependencyObject> , o uno de sus subtipos, al implementar las propiedades de dependencia.</span><span class="sxs-lookup"><span data-stu-id="f510f-107">✔️ DO inherit from <xref:System.Windows.DependencyObject>, or one of its subtypes, when implementing dependency properties.</span></span> <span data-ttu-id="f510f-108">El tipo proporciona una implementación muy eficaz de un almacén de propiedades y admite automáticamente el enlace de datos de WPF.</span><span class="sxs-lookup"><span data-stu-id="f510f-108">The type provides a very efficient implementation of a property store and automatically supports WPF data binding.</span></span>

 <span data-ttu-id="f510f-109">✔️ proporcionan una propiedad CLR normal y un campo estático público de solo lectura que almacena una instancia de <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> para cada propiedad de dependencia.</span><span class="sxs-lookup"><span data-stu-id="f510f-109">✔️ DO provide a regular CLR property and public static read-only field storing an instance of <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> for each dependency property.</span></span>

 <span data-ttu-id="f510f-110">✔️ implementar las propiedades de dependencia mediante una llamada a métodos <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> de instancia y <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f510f-110">✔️ DO implement dependency properties by calling instance methods <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> and <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span></span>

 <span data-ttu-id="f510f-111">✔️ Asigne un nombre al campo estático de la propiedad de dependencia mediante el sufijo del nombre de la propiedad con "Property".</span><span class="sxs-lookup"><span data-stu-id="f510f-111">✔️ DO name the dependency property static field by suffixing the name of the property with "Property."</span></span>

 <span data-ttu-id="f510f-112">❌ NO establezca los valores predeterminados de las propiedades de dependencia explícitamente en el código; establézcalo en Metadata en su lugar.</span><span class="sxs-lookup"><span data-stu-id="f510f-112">❌ DO NOT set default values of dependency properties explicitly in code; set them in metadata instead.</span></span>

 <span data-ttu-id="f510f-113">Si establece explícitamente un valor predeterminado de la propiedad, puede impedir que esa propiedad se establezca mediante algunos medios implícitos, como un estilo.</span><span class="sxs-lookup"><span data-stu-id="f510f-113">If you set a property default explicitly, you might prevent that property from being set by some implicit means, such as a styling.</span></span>

 <span data-ttu-id="f510f-114">❌ No coloque código en los descriptores de acceso de propiedad distintos del código estándar para tener acceso al campo estático.</span><span class="sxs-lookup"><span data-stu-id="f510f-114">❌ DO NOT put code in the property accessors other than the standard code to access the static field.</span></span>

 <span data-ttu-id="f510f-115">Ese código no se ejecutará si la propiedad está establecida por medios implícitos, como un estilo, porque el estilo utiliza el campo estático directamente.</span><span class="sxs-lookup"><span data-stu-id="f510f-115">That code won’t execute if the property is set by implicit means, such as a styling, because styling uses the static field directly.</span></span>

 <span data-ttu-id="f510f-116">❌ No use propiedades de dependencia para almacenar datos seguros.</span><span class="sxs-lookup"><span data-stu-id="f510f-116">❌ DO NOT use dependency properties to store secure data.</span></span> <span data-ttu-id="f510f-117">Incluso se puede tener acceso a las propiedades de dependencia privadas públicamente.</span><span class="sxs-lookup"><span data-stu-id="f510f-117">Even private dependency properties can be accessed publicly.</span></span>

## <a name="attached-dependency-property-design"></a><span data-ttu-id="f510f-118">Diseño de propiedad de dependencia adjunta</span><span class="sxs-lookup"><span data-stu-id="f510f-118">Attached Dependency Property Design</span></span>
 <span data-ttu-id="f510f-119">Las propiedades de dependencia descritas en la sección anterior representan propiedades intrínsecas del tipo declarativo; por ejemplo, la `Text` propiedad es una propiedad de `TextButton` , que la declara.</span><span class="sxs-lookup"><span data-stu-id="f510f-119">Dependency properties described in the preceding section represent intrinsic properties of the declaring type; for example, the `Text` property is a property of `TextButton`, which declares it.</span></span> <span data-ttu-id="f510f-120">Un tipo especial de propiedad de dependencia es la propiedad de dependencia asociada.</span><span class="sxs-lookup"><span data-stu-id="f510f-120">A special kind of dependency property is the attached dependency property.</span></span>

 <span data-ttu-id="f510f-121">Un ejemplo clásico de una propiedad adjunta es la <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f510f-121">A classic example of an attached property is the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="f510f-122">La propiedad representa la posición de la columna del botón (no de la cuadrícula), pero solo es relevante si el botón está contenido en una cuadrícula, por lo que está "adjunto" a los botones por cuadrículas.</span><span class="sxs-lookup"><span data-stu-id="f510f-122">The property represents Button’s (not Grid’s) column position, but it is only relevant if the Button is contained in a Grid, and so it's "attached" to Buttons by Grids.</span></span>

```xaml
<Grid>
    <Grid.ColumnDefinitions>
        <ColumnDefinition />
        <ColumnDefinition />
    </Grid.ColumnDefinitions>

    <Button Grid.Column="0">Click</Button>
    <Button Grid.Column="1">Clack</Button>
</Grid>
```

 <span data-ttu-id="f510f-123">La definición de una propiedad adjunta es principalmente similar a la de una propiedad de dependencia normal, con la excepción de que los descriptores de acceso se representan mediante métodos estáticos get y set:</span><span class="sxs-lookup"><span data-stu-id="f510f-123">The definition of an attached property looks mostly like that of a regular dependency property, except that the accessors are represented by static Get and Set methods:</span></span>

```csharp
public class Grid {

    public static int GetColumn(DependencyObject obj) {
        return (int)obj.GetValue(ColumnProperty);
    }

    public static void SetColumn(DependencyObject obj, int value) {
        obj.SetValue(ColumnProperty,value);
    }

    public static readonly DependencyProperty ColumnProperty =
        DependencyProperty.RegisterAttached(
            "Column",
            typeof(int),
            typeof(Grid)
    );
}
```

## <a name="dependency-property-validation"></a><span data-ttu-id="f510f-124">Validación de propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="f510f-124">Dependency Property Validation</span></span>
 <span data-ttu-id="f510f-125">A menudo, las propiedades implementan lo que se denomina validación.</span><span class="sxs-lookup"><span data-stu-id="f510f-125">Properties often implement what is called validation.</span></span> <span data-ttu-id="f510f-126">La lógica de validación se ejecuta cuando se realiza un intento de cambiar el valor de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="f510f-126">Validation logic executes when an attempt is made to change the value of a property.</span></span>

 <span data-ttu-id="f510f-127">Desafortunadamente, los descriptores de acceso de propiedad de dependencia no pueden contener código de validación arbitrario.</span><span class="sxs-lookup"><span data-stu-id="f510f-127">Unfortunately dependency property accessors cannot contain arbitrary validation code.</span></span> <span data-ttu-id="f510f-128">En su lugar, se debe especificar la lógica de validación de la propiedad de dependencia durante el registro de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="f510f-128">Instead, dependency property validation logic needs to be specified during property registration.</span></span>

 <span data-ttu-id="f510f-129">❌ No coloque la lógica de validación de propiedades de dependencia en los descriptores de acceso de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="f510f-129">❌ DO NOT put dependency property validation logic in the property’s accessors.</span></span> <span data-ttu-id="f510f-130">En su lugar, pase una devolución de llamada de validación al `DependencyProperty.Register` método.</span><span class="sxs-lookup"><span data-stu-id="f510f-130">Instead, pass a validation callback to `DependencyProperty.Register` method.</span></span>

## <a name="dependency-property-change-notifications"></a><span data-ttu-id="f510f-131">Notificaciones de cambio de propiedad de dependencia</span><span class="sxs-lookup"><span data-stu-id="f510f-131">Dependency Property Change Notifications</span></span>
 <span data-ttu-id="f510f-132">❌ No implemente la lógica de notificación de cambios en los descriptores de acceso de propiedad de dependencia.</span><span class="sxs-lookup"><span data-stu-id="f510f-132">❌ DO NOT implement change notification logic in dependency property accessors.</span></span> <span data-ttu-id="f510f-133">Las propiedades de dependencia tienen una característica de notificaciones de cambio integrada que se debe usar proporcionando una devolución de llamada de notificación de cambios al <xref:System.Windows.PropertyMetadata> .</span><span class="sxs-lookup"><span data-stu-id="f510f-133">Dependency properties have a built-in change notifications feature that must be used by supplying a change notification callback to the <xref:System.Windows.PropertyMetadata>.</span></span>

## <a name="dependency-property-value-coercion"></a><span data-ttu-id="f510f-134">Coerción de valores de propiedad de dependencia</span><span class="sxs-lookup"><span data-stu-id="f510f-134">Dependency Property Value Coercion</span></span>
 <span data-ttu-id="f510f-135">La conversión de propiedad tiene lugar cuando el valor dado a un establecedor de propiedad lo modifica el establecedor antes de que se modifique realmente el almacén de propiedades.</span><span class="sxs-lookup"><span data-stu-id="f510f-135">Property coercion takes place when the value given to a property setter is modified by the setter before the property store is actually modified.</span></span>

 <span data-ttu-id="f510f-136">❌ No implemente la lógica de coerción en los descriptores de acceso de propiedad de dependencia.</span><span class="sxs-lookup"><span data-stu-id="f510f-136">❌ DO NOT implement coercion logic in dependency property accessors.</span></span>

 <span data-ttu-id="f510f-137">Las propiedades de dependencia tienen una característica de coerción integrada y se pueden usar proporcionando una devolución de llamada de coerción a `PropertyMetadata` .</span><span class="sxs-lookup"><span data-stu-id="f510f-137">Dependency properties have a built-in coercion feature, and it can be used by supplying a coercion callback to the `PropertyMetadata`.</span></span>

 <span data-ttu-id="f510f-138">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="f510f-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="f510f-139">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="f510f-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="f510f-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f510f-140">See also</span></span>

- [<span data-ttu-id="f510f-141">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="f510f-141">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="f510f-142">Modelos de diseño comunes</span><span class="sxs-lookup"><span data-stu-id="f510f-142">Common Design Patterns</span></span>](common-design-patterns.md)
