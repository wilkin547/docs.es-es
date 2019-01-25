---
title: Propiedades de dependencia
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
author: KrzysztofCwalina
ms.openlocfilehash: 52d7a69a3f52c67ebff3f3db1daf0790e995913a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722037"
---
# <a name="dependency-properties"></a><span data-ttu-id="fc8bd-102">Propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="fc8bd-102">Dependency Properties</span></span>
<span data-ttu-id="fc8bd-103">Una propiedad de dependencia (DP) es una propiedad normal que almacena su valor en un almacén de propiedades en lugar de almacenarlas en una variable de tipo (campo), por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-103">A dependency property (DP) is a regular property that stores its value in a property store instead of storing it in a type variable (field), for example.</span></span>  
  
 <span data-ttu-id="fc8bd-104">Una propiedad de dependencia adjunta es un tipo de propiedad de dependencia que se modelan como métodos estáticos de Get y Set, que representa "propiedades" que describen las relaciones entre objetos y sus contenedores (por ejemplo, la posición de un `Button` objeto en un `Panel` contenedor).</span><span class="sxs-lookup"><span data-stu-id="fc8bd-104">An attached dependency property is a kind of dependency property modeled as static Get and Set methods representing "properties" describing relationships between objects and their containers (e.g., the position of a `Button` object on a `Panel` container).</span></span>  
  
 <span data-ttu-id="fc8bd-105">**✓ DO** proporcionan las propiedades de dependencia, si tiene las propiedades para admitir las características de WPF como un estilo, desencadenadores, enlace de datos, animaciones, recursos dinámicos y herencia.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-105">**✓ DO** provide the dependency properties, if you need the properties to support WPF features such as styling, triggers, data binding, animations, dynamic resources, and inheritance.</span></span>  
  
## <a name="dependency-property-design"></a><span data-ttu-id="fc8bd-106">Diseño de la propiedad de dependencia</span><span class="sxs-lookup"><span data-stu-id="fc8bd-106">Dependency Property Design</span></span>  
 <span data-ttu-id="fc8bd-107">**✓ DO** heredarlo <xref:System.Windows.DependencyObject>, o uno de sus subtipos, al implementar propiedades de dependencia.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-107">**✓ DO** inherit from <xref:System.Windows.DependencyObject>, or one of its subtypes, when implementing dependency properties.</span></span> <span data-ttu-id="fc8bd-108">El tipo proporciona una implementación muy eficaz de un almacén de propiedades y admite automáticamente el enlace de datos WPF.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-108">The type provides a very efficient implementation of a property store and automatically supports WPF data binding.</span></span>  
  
 <span data-ttu-id="fc8bd-109">**✓ DO** proporcionar una propiedad CLR normal y el campo estático público de solo lectura almacenar una instancia de <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> para cada propiedad de dependencia.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-109">**✓ DO** provide a regular CLR property and public static read-only field storing an instance of <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> for each dependency property.</span></span>  
  
 <span data-ttu-id="fc8bd-110">**✓ DO** implementar propiedades de dependencia mediante una llamada a métodos de instancia <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> y <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-110">**✓ DO** implement dependency properties by calling instance methods <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> and <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="fc8bd-111">**✓ DO** el nombre del campo estático de propiedad de dependencia aplicando el sufijo del nombre de la propiedad con "Property".</span><span class="sxs-lookup"><span data-stu-id="fc8bd-111">**✓ DO** name the dependency property static field by suffixing the name of the property with "Property."</span></span>  
  
 <span data-ttu-id="fc8bd-112">**X DO NOT** establecer valores predeterminados de las propiedades de dependencia explícitamente en código; establecidos en metadatos.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-112">**X DO NOT** set default values of dependency properties explicitly in code; set them in metadata instead.</span></span>  
  
 <span data-ttu-id="fc8bd-113">Si establece explícitamente un valor predeterminado de la propiedad, puede impedir que esa propiedad se establece por medios implícitas, por ejemplo, una aplicación de estilos.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-113">If you set a property default explicitly, you might prevent that property from being set by some implicit means, such as a styling.</span></span>  
  
 <span data-ttu-id="fc8bd-114">**X DO NOT** colocar código en los descriptores de acceso de propiedad que no sea el código estándar para tener acceso al campo estático.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-114">**X DO NOT** put code in the property accessors other than the standard code to access the static field.</span></span>  
  
 <span data-ttu-id="fc8bd-115">Que no ejecute código si la propiedad se establece por medios implícitas, como una aplicación de estilos, porque la aplicación de estilos utiliza el campo estático directamente.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-115">That code won’t execute if the property is set by implicit means, such as a styling, because styling uses the static field directly.</span></span>  
  
 <span data-ttu-id="fc8bd-116">**X DO NOT** utilizar propiedades de dependencia para almacenar los datos seguros.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-116">**X DO NOT** use dependency properties to store secure data.</span></span> <span data-ttu-id="fc8bd-117">Las propiedades de dependencia incluso privada es accesible públicamente.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-117">Even private dependency properties can be accessed publicly.</span></span>  
  
## <a name="attached-dependency-property-design"></a><span data-ttu-id="fc8bd-118">Diseño de la propiedad de dependencia adjunta</span><span class="sxs-lookup"><span data-stu-id="fc8bd-118">Attached Dependency Property Design</span></span>  
 <span data-ttu-id="fc8bd-119">Las propiedades de dependencia que se describe en la sección anterior representan las propiedades intrínsecas del tipo declarativo. Por ejemplo, el `Text` es una propiedad del `TextButton`, que declara.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-119">Dependency properties described in the preceding section represent intrinsic properties of the declaring type; for example, the `Text` property is a property of `TextButton`, which declares it.</span></span> <span data-ttu-id="fc8bd-120">Un tipo especial de propiedad de dependencia es la propiedad de dependencia adjunta.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-120">A special kind of dependency property is the attached dependency property.</span></span>  
  
 <span data-ttu-id="fc8bd-121">Un ejemplo clásico de una propiedad adjunta es la <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-121">A classic example of an attached property is the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="fc8bd-122">La propiedad representa la posición de la columna del botón (no de la cuadrícula), pero solo es pertinente si el botón se encuentra en una cuadrícula, por lo que está "conectado" a los botones mediante cuadrículas.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-122">The property represents Button’s (not Grid’s) column position, but it is only relevant if the Button is contained in a Grid, and so it's "attached" to Buttons by Grids.</span></span>  
  
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
  
 <span data-ttu-id="fc8bd-123">La definición de una propiedad adjunta aspecto en su mayor parte de una propiedad de dependencia normal, excepto en que los descriptores de acceso se representan mediante los métodos Get y Set estáticos:</span><span class="sxs-lookup"><span data-stu-id="fc8bd-123">The definition of an attached property looks mostly like that of a regular dependency property, except that the accessors are represented by static Get and Set methods:</span></span>  
  
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
  
## <a name="dependency-property-validation"></a><span data-ttu-id="fc8bd-124">Validación de propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="fc8bd-124">Dependency Property Validation</span></span>  
 <span data-ttu-id="fc8bd-125">Las propiedades suelen implementar lo que se denomina validación.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-125">Properties often implement what is called validation.</span></span> <span data-ttu-id="fc8bd-126">Lógica de validación se ejecuta cuando se realiza un intento para cambiar el valor de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-126">Validation logic executes when an attempt is made to change the value of a property.</span></span>  
  
 <span data-ttu-id="fc8bd-127">Lamentablemente, los descriptores de acceso de propiedad de dependencia no pueden contener código de validación arbitraria.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-127">Unfortunately dependency property accessors cannot contain arbitrary validation code.</span></span> <span data-ttu-id="fc8bd-128">En su lugar, lógica de validación de propiedad de dependencia debe especificarse durante el registro de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-128">Instead, dependency property validation logic needs to be specified during property registration.</span></span>  
  
 <span data-ttu-id="fc8bd-129">**X DO NOT** colocar lógica de validación de propiedad de dependencia en los descriptores de acceso de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-129">**X DO NOT** put dependency property validation logic in the property’s accessors.</span></span> <span data-ttu-id="fc8bd-130">En su lugar, pase una devolución de llamada de validación para `DependencyProperty.Register` método.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-130">Instead, pass a validation callback to `DependencyProperty.Register` method.</span></span>  
  
## <a name="dependency-property-change-notifications"></a><span data-ttu-id="fc8bd-131">Notificaciones de cambio de propiedad de dependencia</span><span class="sxs-lookup"><span data-stu-id="fc8bd-131">Dependency Property Change Notifications</span></span>  
 <span data-ttu-id="fc8bd-132">**X DO NOT** implementar la lógica de la notificación de cambio de descriptores de acceso de propiedad de dependencia.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-132">**X DO NOT** implement change notification logic in dependency property accessors.</span></span> <span data-ttu-id="fc8bd-133">Propiedades de dependencia tienen una característica de notificaciones de cambios integrado que se debe usar si se suministra una devolución de llamada de notificación de cambio para el <xref:System.Windows.PropertyMetadata>.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-133">Dependency properties have a built-in change notifications feature that must be used by supplying a change notification callback to the <xref:System.Windows.PropertyMetadata>.</span></span>  
  
## <a name="dependency-property-value-coercion"></a><span data-ttu-id="fc8bd-134">Conversión del valor de propiedad de dependencia</span><span class="sxs-lookup"><span data-stu-id="fc8bd-134">Dependency Property Value Coercion</span></span>  
 <span data-ttu-id="fc8bd-135">Conversión de propiedad tiene lugar cuando se modifica el valor dado para un establecedor de propiedades por el establecedor antes de que realmente se modifica el almacén de propiedades.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-135">Property coercion takes place when the value given to a property setter is modified by the setter before the property store is actually modified.</span></span>  
  
 <span data-ttu-id="fc8bd-136">**X DO NOT** implementar la lógica de conversión de los descriptores de acceso de propiedad de dependencia.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-136">**X DO NOT** implement coercion logic in dependency property accessors.</span></span>  
  
 <span data-ttu-id="fc8bd-137">Propiedades de dependencia tienen una característica de coerción integrada y se puede usar proporcionando una devolución de llamada coerción la `PropertyMetadata`.</span><span class="sxs-lookup"><span data-stu-id="fc8bd-137">Dependency properties have a built-in coercion feature, and it can be used by supplying a coercion callback to the `PropertyMetadata`.</span></span>  
  
 <span data-ttu-id="fc8bd-138">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="fc8bd-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="fc8bd-139">*Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="fc8bd-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc8bd-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc8bd-140">See also</span></span>

- [<span data-ttu-id="fc8bd-141">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fc8bd-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="fc8bd-142">Patrones de diseño comunes</span><span class="sxs-lookup"><span data-stu-id="fc8bd-142">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)
