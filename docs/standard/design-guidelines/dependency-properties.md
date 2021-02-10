---
description: 'Más información acerca de: Propiedades de dependencia'
title: Propiedades de dependencia
ms.date: 10/22/2008
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
ms.openlocfilehash: 78b141d6e8d1bb6bd5cf050a89aa67705111bae3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642310"
---
# <a name="dependency-properties"></a><span data-ttu-id="5a1e6-103">Propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="5a1e6-103">Dependency Properties</span></span>

<span data-ttu-id="5a1e6-104">Una propiedad de dependencia es una propiedad normal que almacena su valor en un almacén de propiedades en lugar de en una variable de tipo (campo), por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-104">A dependency property (DP) is a regular property that stores its value in a property store instead of storing it in a type variable (field), for example.</span></span>

 <span data-ttu-id="5a1e6-105">Una propiedad de dependencia adjunta es un tipo de propiedad de dependencia modelada como métodos estáticos Get y Set que representan "propiedades" que describen las relaciones entre objetos y sus contenedores (por ejemplo, la posición de un objeto `Button` en un contenedor `Panel`).</span><span class="sxs-lookup"><span data-stu-id="5a1e6-105">An attached dependency property is a kind of dependency property modeled as static Get and Set methods representing "properties" describing relationships between objects and their containers (e.g., the position of a `Button` object on a `Panel` container).</span></span>

 <span data-ttu-id="5a1e6-106">✔️ Proporcione las propiedades de dependencia, si necesita que las propiedades admitan características de WPF como la aplicación de estilos, los desencadenadores, el enlace de datos, las animaciones, los recursos dinámicos y la herencia.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-106">✔️ DO provide the dependency properties, if you need the properties to support WPF features such as styling, triggers, data binding, animations, dynamic resources, and inheritance.</span></span>

## <a name="dependency-property-design"></a><span data-ttu-id="5a1e6-107">Diseño de propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="5a1e6-107">Dependency Property Design</span></span>

 <span data-ttu-id="5a1e6-108">✔️ Herede de <xref:System.Windows.DependencyObject>, o de uno de sus subtipos, al implementar las propiedades de dependencia.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-108">✔️ DO inherit from <xref:System.Windows.DependencyObject>, or one of its subtypes, when implementing dependency properties.</span></span> <span data-ttu-id="5a1e6-109">El tipo proporciona una implementación muy eficaz de un almacén de propiedades y admite automáticamente el enlace de datos de WPF.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-109">The type provides a very efficient implementation of a property store and automatically supports WPF data binding.</span></span>

 <span data-ttu-id="5a1e6-110">✔️ Proporcione una propiedad de CLR normal y un campo estático público de solo lectura que almacene una instancia de <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> para cada propiedad de dependencia.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-110">✔️ DO provide a regular CLR property and public static read-only field storing an instance of <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> for each dependency property.</span></span>

 <span data-ttu-id="5a1e6-111">✔️ Implemente las propiedades de dependencia llamando a los métodos de instancia <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> y <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-111">✔️ DO implement dependency properties by calling instance methods <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> and <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span></span>

 <span data-ttu-id="5a1e6-112">✔️ Asigne un nombre al campo estático de la propiedad de dependencia mediante el sufijo del nombre de la propiedad con "Property".</span><span class="sxs-lookup"><span data-stu-id="5a1e6-112">✔️ DO name the dependency property static field by suffixing the name of the property with "Property."</span></span>

 <span data-ttu-id="5a1e6-113">❌ NO establezca los valores predeterminados de las propiedades de dependencia explícitamente en el código; hágalo en los metadatos.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-113">❌ DO NOT set default values of dependency properties explicitly in code; set them in metadata instead.</span></span>

 <span data-ttu-id="5a1e6-114">Si establece explícitamente un valor predeterminado de propiedad, puede impedir que esa propiedad se establezca mediante algunos medios implícitos, como una aplicación de estilos.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-114">If you set a property default explicitly, you might prevent that property from being set by some implicit means, such as a styling.</span></span>

 <span data-ttu-id="5a1e6-115">❌ NO coloque código en descriptores de acceso de propiedad que no sean el código estándar para tener acceso al campo estático.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-115">❌ DO NOT put code in the property accessors other than the standard code to access the static field.</span></span>

 <span data-ttu-id="5a1e6-116">Ese código no se ejecutará si la propiedad está establecida por medios implícitos, como una aplicación de estilos, porque la aplicación de estilos utiliza el campo estático directamente.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-116">That code won’t execute if the property is set by implicit means, such as a styling, because styling uses the static field directly.</span></span>

 <span data-ttu-id="5a1e6-117">❌ NO use propiedades de dependencia para almacenar datos seguros.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-117">❌ DO NOT use dependency properties to store secure data.</span></span> <span data-ttu-id="5a1e6-118">Incluso a las propiedades privadas de las dependencias se puede acceder públicamente.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-118">Even private dependency properties can be accessed publicly.</span></span>

## <a name="attached-dependency-property-design"></a><span data-ttu-id="5a1e6-119">Diseño de las propiedades de dependencia adjuntas</span><span class="sxs-lookup"><span data-stu-id="5a1e6-119">Attached Dependency Property Design</span></span>

 <span data-ttu-id="5a1e6-120">Las propiedades de dependencia descritas en la sección anterior representan propiedades intrínsecas del tipo declarativo; por ejemplo, la propiedad `Text` es una propiedad de `TextButton`, que la declara.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-120">Dependency properties described in the preceding section represent intrinsic properties of the declaring type; for example, the `Text` property is a property of `TextButton`, which declares it.</span></span> <span data-ttu-id="5a1e6-121">Un tipo especial de propiedad de dependencia es la propiedad de dependencia adjunta.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-121">A special kind of dependency property is the attached dependency property.</span></span>

 <span data-ttu-id="5a1e6-122">Un ejemplo clásico de una propiedad adjunta es la propiedad <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-122">A classic example of an attached property is the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="5a1e6-123">La propiedad representa la posición de la columna del botón (no de la cuadrícula), pero solo es relevante si el botón está contenido en una cuadrícula, por lo que está "adjunta" a los botones mediante cuadrículas.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-123">The property represents Button’s (not Grid’s) column position, but it is only relevant if the Button is contained in a Grid, and so it's "attached" to Buttons by Grids.</span></span>

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

 <span data-ttu-id="5a1e6-124">La definición de una propiedad adjunta se parece en gran medida a la de una propiedad de dependencia normal, con la excepción de que los descriptores de acceso se representan mediante los métodos estáticos Get y Set:</span><span class="sxs-lookup"><span data-stu-id="5a1e6-124">The definition of an attached property looks mostly like that of a regular dependency property, except that the accessors are represented by static Get and Set methods:</span></span>

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

## <a name="dependency-property-validation"></a><span data-ttu-id="5a1e6-125">Validación de propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="5a1e6-125">Dependency Property Validation</span></span>

 <span data-ttu-id="5a1e6-126">A menudo, las propiedades implementan lo que se denomina "validación".</span><span class="sxs-lookup"><span data-stu-id="5a1e6-126">Properties often implement what is called validation.</span></span> <span data-ttu-id="5a1e6-127">La lógica de validación se ejecuta cuando se realiza un intento de cambiar el valor de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-127">Validation logic executes when an attempt is made to change the value of a property.</span></span>

 <span data-ttu-id="5a1e6-128">Lamentablemente, los descriptores de acceso de propiedades de dependencia no pueden contener código de validación arbitrario.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-128">Unfortunately dependency property accessors cannot contain arbitrary validation code.</span></span> <span data-ttu-id="5a1e6-129">En su lugar, se debe especificar la lógica de validación de la propiedad de dependencia durante el registro de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-129">Instead, dependency property validation logic needs to be specified during property registration.</span></span>

 <span data-ttu-id="5a1e6-130">❌ NO coloque la lógica de validación de propiedades de dependencia en los descriptores de acceso de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-130">❌ DO NOT put dependency property validation logic in the property’s accessors.</span></span> <span data-ttu-id="5a1e6-131">En su lugar, pase una devolución de llamada de validación al método `DependencyProperty.Register`.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-131">Instead, pass a validation callback to `DependencyProperty.Register` method.</span></span>

## <a name="dependency-property-change-notifications"></a><span data-ttu-id="5a1e6-132">Notificaciones de cambios de propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="5a1e6-132">Dependency Property Change Notifications</span></span>

 <span data-ttu-id="5a1e6-133">❌ NO implemente la lógica de notificación de cambios en descriptores de acceso de propiedades de dependencia.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-133">❌ DO NOT implement change notification logic in dependency property accessors.</span></span> <span data-ttu-id="5a1e6-134">Las propiedades de dependencia tienen una característica de notificaciones de cambio integrada que se debe usar proporcionando una devolución de llamada de notificación de cambio a <xref:System.Windows.PropertyMetadata>.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-134">Dependency properties have a built-in change notifications feature that must be used by supplying a change notification callback to the <xref:System.Windows.PropertyMetadata>.</span></span>

## <a name="dependency-property-value-coercion"></a><span data-ttu-id="5a1e6-135">Coerción de valores de propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="5a1e6-135">Dependency Property Value Coercion</span></span>

 <span data-ttu-id="5a1e6-136">La coerción de propiedades se produce cuando el valor dado a un establecedor de propiedad lo modifica el establecedor antes de que se modifique realmente el almacén de propiedades.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-136">Property coercion takes place when the value given to a property setter is modified by the setter before the property store is actually modified.</span></span>

 <span data-ttu-id="5a1e6-137">❌ NO implemente la lógica de coerción en descriptores de acceso de propiedades de dependencia.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-137">❌ DO NOT implement coercion logic in dependency property accessors.</span></span>

 <span data-ttu-id="5a1e6-138">Las propiedades de dependencia tienen una característica de coerción integrada y se pueden usar proporcionando una devolución de llamada de coerción a `PropertyMetadata`.</span><span class="sxs-lookup"><span data-stu-id="5a1e6-138">Dependency properties have a built-in coercion feature, and it can be used by supplying a coercion callback to the `PropertyMetadata`.</span></span>

 <span data-ttu-id="5a1e6-139">*Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="5a1e6-139">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="5a1e6-140">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="5a1e6-140">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="5a1e6-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a1e6-141">See also</span></span>

- [<span data-ttu-id="5a1e6-142">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5a1e6-142">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="5a1e6-143">Patrones de diseño comunes</span><span class="sxs-lookup"><span data-stu-id="5a1e6-143">Common Design Patterns</span></span>](common-design-patterns.md)
