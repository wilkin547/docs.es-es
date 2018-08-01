---
title: Propiedades de dependencia
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7398202cc265fbd55b9bf0b5a53367dedcab57b0
ms.sourcegitcommit: ed7b4b9b77d35e94a35a2634e8c874f46603fb2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2018
ms.locfileid: "36948490"
---
# <a name="dependency-properties"></a><span data-ttu-id="0200b-102">Propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="0200b-102">Dependency Properties</span></span>
<span data-ttu-id="0200b-103">Una propiedad de dependencia (DP) es una propiedad normal que almacena su valor en un almacén de propiedades en lugar de almacenar en una variable de tipo (campo), por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0200b-103">A dependency property (DP) is a regular property that stores its value in a property store instead of storing it in a type variable (field), for example.</span></span>  
  
 <span data-ttu-id="0200b-104">Una propiedad de dependencia adjunta es un tipo de propiedad de dependencia que se modelan como métodos estáticos de Get y Set, que representa "propiedades" que describen las relaciones entre objetos y sus contenedores (por ejemplo, la posición de un `Button` objeto en un `Panel` contenedor).</span><span class="sxs-lookup"><span data-stu-id="0200b-104">An attached dependency property is a kind of dependency property modeled as static Get and Set methods representing "properties" describing relationships between objects and their containers (e.g., the position of a `Button` object on a `Panel` container).</span></span>  
  
 <span data-ttu-id="0200b-105">**✓ DO** proporcionan las propiedades de dependencia, si tiene las propiedades para admitir las características de WPF como un estilo, desencadenadores, enlace de datos, animaciones, recursos dinámicos y herencia.</span><span class="sxs-lookup"><span data-stu-id="0200b-105">**✓ DO** provide the dependency properties, if you need the properties to support WPF features such as styling, triggers, data binding, animations, dynamic resources, and inheritance.</span></span>  
  
## <a name="dependency-property-design"></a><span data-ttu-id="0200b-106">Diseño de la propiedad de dependencia</span><span class="sxs-lookup"><span data-stu-id="0200b-106">Dependency Property Design</span></span>  
 <span data-ttu-id="0200b-107">**✓ DO** heredarlo <xref:System.Windows.DependencyObject>, o uno de sus subtipos, al implementar propiedades de dependencia.</span><span class="sxs-lookup"><span data-stu-id="0200b-107">**✓ DO** inherit from <xref:System.Windows.DependencyObject>, or one of its subtypes, when implementing dependency properties.</span></span> <span data-ttu-id="0200b-108">El tipo proporciona una implementación muy eficaz de un almacén de propiedades y automáticamente admite enlace de datos WPF.</span><span class="sxs-lookup"><span data-stu-id="0200b-108">The type provides a very efficient implementation of a property store and automatically supports WPF data binding.</span></span>  
  
 <span data-ttu-id="0200b-109">**✓ DO** proporcionar una propiedad CLR normal y el campo estático público de solo lectura almacenar una instancia de <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> para cada propiedad de dependencia.</span><span class="sxs-lookup"><span data-stu-id="0200b-109">**✓ DO** provide a regular CLR property and public static read-only field storing an instance of <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> for each dependency property.</span></span>  
  
 <span data-ttu-id="0200b-110">**✓ DO** implementar propiedades de dependencia mediante una llamada a métodos de instancia <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> y <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0200b-110">**✓ DO** implement dependency properties by calling instance methods <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> and <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="0200b-111">**✓ DO** el nombre del campo estático de propiedad de dependencia aplicando el sufijo del nombre de la propiedad con "Property".</span><span class="sxs-lookup"><span data-stu-id="0200b-111">**✓ DO** name the dependency property static field by suffixing the name of the property with "Property."</span></span>  
  
 <span data-ttu-id="0200b-112">**X DO NOT** establecer valores predeterminados de las propiedades de dependencia explícitamente en código; establecidos en metadatos.</span><span class="sxs-lookup"><span data-stu-id="0200b-112">**X DO NOT** set default values of dependency properties explicitly in code; set them in metadata instead.</span></span>  
  
 <span data-ttu-id="0200b-113">Si se establece explícitamente un valor predeterminado de la propiedad, puede impedir que algunos medios implícita, por ejemplo, un estilo que se va a establecer esa propiedad.</span><span class="sxs-lookup"><span data-stu-id="0200b-113">If you set a property default explicitly, you might prevent that property from being set by some implicit means, such as a styling.</span></span>  
  
 <span data-ttu-id="0200b-114">**X DO NOT** colocar código en los descriptores de acceso de propiedad que no sea el código estándar para tener acceso al campo estático.</span><span class="sxs-lookup"><span data-stu-id="0200b-114">**X DO NOT** put code in the property accessors other than the standard code to access the static field.</span></span>  
  
 <span data-ttu-id="0200b-115">Que no ejecute código si la propiedad se establece de forma implícita, como un estilo, porque la aplicación de estilos utiliza directamente el campo estático.</span><span class="sxs-lookup"><span data-stu-id="0200b-115">That code won’t execute if the property is set by implicit means, such as a styling, because styling uses the static field directly.</span></span>  
  
 <span data-ttu-id="0200b-116">**X DO NOT** utilizar propiedades de dependencia para almacenar los datos seguros.</span><span class="sxs-lookup"><span data-stu-id="0200b-116">**X DO NOT** use dependency properties to store secure data.</span></span> <span data-ttu-id="0200b-117">Propiedades de dependencia incluso privada pueden tener acceso públicamente.</span><span class="sxs-lookup"><span data-stu-id="0200b-117">Even private dependency properties can be accessed publicly.</span></span>  
  
## <a name="attached-dependency-property-design"></a><span data-ttu-id="0200b-118">Diseño de la propiedad de dependencia adjunta</span><span class="sxs-lookup"><span data-stu-id="0200b-118">Attached Dependency Property Design</span></span>  
 <span data-ttu-id="0200b-119">Propiedades de dependencia que se describe en la sección anterior representan propiedades intrínsecas del tipo declarativo; Por ejemplo, el `Text` es una propiedad del `TextButton`, que lo declara.</span><span class="sxs-lookup"><span data-stu-id="0200b-119">Dependency properties described in the preceding section represent intrinsic properties of the declaring type; for example, the `Text` property is a property of `TextButton`, which declares it.</span></span> <span data-ttu-id="0200b-120">Un tipo especial de propiedad de dependencia es la propiedad de dependencia adjunta.</span><span class="sxs-lookup"><span data-stu-id="0200b-120">A special kind of dependency property is the attached dependency property.</span></span>  
  
 <span data-ttu-id="0200b-121">Un ejemplo clásico de una propiedad adjunta es la <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="0200b-121">A classic example of an attached property is the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="0200b-122">La propiedad representa la posición de la columna del botón (no la cuadrícula), pero solo es pertinente si el botón está contenido en una cuadrícula, por lo que se "une" a los botones mediante cuadrículas.</span><span class="sxs-lookup"><span data-stu-id="0200b-122">The property represents Button’s (not Grid’s) column position, but it is only relevant if the Button is contained in a Grid, and so it's "attached" to Buttons by Grids.</span></span>  
  
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
  
 <span data-ttu-id="0200b-123">La definición de una propiedad adjunta es principalmente similar de una propiedad de dependencia normal, excepto en que los descriptores de acceso se representan mediante los métodos Get y Set estáticos:</span><span class="sxs-lookup"><span data-stu-id="0200b-123">The definition of an attached property looks mostly like that of a regular dependency property, except that the accessors are represented by static Get and Set methods:</span></span>  
  
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
  
## <a name="dependency-property-validation"></a><span data-ttu-id="0200b-124">Validación de propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="0200b-124">Dependency Property Validation</span></span>  
 <span data-ttu-id="0200b-125">Propiedades implementan a menudo lo que se denomina validación.</span><span class="sxs-lookup"><span data-stu-id="0200b-125">Properties often implement what is called validation.</span></span> <span data-ttu-id="0200b-126">Lógica de validación se ejecuta cuando se realiza un intento para cambiar el valor de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="0200b-126">Validation logic executes when an attempt is made to change the value of a property.</span></span>  
  
 <span data-ttu-id="0200b-127">Lamentablemente descriptores de acceso de propiedad de dependencia no pueden contener código de validación arbitraria.</span><span class="sxs-lookup"><span data-stu-id="0200b-127">Unfortunately dependency property accessors cannot contain arbitrary validation code.</span></span> <span data-ttu-id="0200b-128">En su lugar, lógica de validación de propiedad de dependencia debe especificarse durante el registro de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="0200b-128">Instead, dependency property validation logic needs to be specified during property registration.</span></span>  
  
 <span data-ttu-id="0200b-129">**X DO NOT** colocar lógica de validación de propiedad de dependencia en los descriptores de acceso de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="0200b-129">**X DO NOT** put dependency property validation logic in the property’s accessors.</span></span> <span data-ttu-id="0200b-130">En su lugar, pase una devolución de llamada de validación para `DependencyProperty.Register` método.</span><span class="sxs-lookup"><span data-stu-id="0200b-130">Instead, pass a validation callback to `DependencyProperty.Register` method.</span></span>  
  
## <a name="dependency-property-change-notifications"></a><span data-ttu-id="0200b-131">Notificaciones de cambio de propiedad de dependencia</span><span class="sxs-lookup"><span data-stu-id="0200b-131">Dependency Property Change Notifications</span></span>  
 <span data-ttu-id="0200b-132">**X DO NOT** implementar la lógica de la notificación de cambio de descriptores de acceso de propiedad de dependencia.</span><span class="sxs-lookup"><span data-stu-id="0200b-132">**X DO NOT** implement change notification logic in dependency property accessors.</span></span> <span data-ttu-id="0200b-133">Propiedades de dependencia tienen una característica de notificaciones de cambios integrada que se debe usar si se suministra una devolución de llamada de notificación de cambio para el <xref:System.Windows.PropertyMetadata>.</span><span class="sxs-lookup"><span data-stu-id="0200b-133">Dependency properties have a built-in change notifications feature that must be used by supplying a change notification callback to the <xref:System.Windows.PropertyMetadata>.</span></span>  
  
## <a name="dependency-property-value-coercion"></a><span data-ttu-id="0200b-134">Conversión de valor de propiedad de dependencia</span><span class="sxs-lookup"><span data-stu-id="0200b-134">Dependency Property Value Coercion</span></span>  
 <span data-ttu-id="0200b-135">Conversión de propiedad tiene lugar cuando se modifica el valor dado un establecedor de propiedad por el establecedor antes de que realmente se modifica el almacén de propiedades.</span><span class="sxs-lookup"><span data-stu-id="0200b-135">Property coercion takes place when the value given to a property setter is modified by the setter before the property store is actually modified.</span></span>  
  
 <span data-ttu-id="0200b-136">**X DO NOT** implementar la lógica de conversión de los descriptores de acceso de propiedad de dependencia.</span><span class="sxs-lookup"><span data-stu-id="0200b-136">**X DO NOT** implement coercion logic in dependency property accessors.</span></span>  
  
 <span data-ttu-id="0200b-137">Propiedades de dependencia tienen una característica integrada la conversión, y se puede utilizar si se suministra una devolución de llamada de conversión para el `PropertyMetadata`.</span><span class="sxs-lookup"><span data-stu-id="0200b-137">Dependency properties have a built-in coercion feature, and it can be used by supplying a coercion callback to the `PropertyMetadata`.</span></span>  
  
 <span data-ttu-id="0200b-138">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="0200b-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="0200b-139">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="0200b-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0200b-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="0200b-140">See Also</span></span>  
 [<span data-ttu-id="0200b-141">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0200b-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="0200b-142">Patrones de diseño comunes</span><span class="sxs-lookup"><span data-stu-id="0200b-142">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)
