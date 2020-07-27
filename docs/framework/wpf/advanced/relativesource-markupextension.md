---
title: Extensión de marcado RelativeSource
description: Especifica las propiedades de un origen de enlace RelativeSource, dentro de una extensión de marcado de enlace, o al establecer la propiedad RelativeSource de un enlace en XAML.
ms.date: 03/30/2017
f1_keywords:
- RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
ms.openlocfilehash: 2da702d23413651a85b45404e088f6708546cc25
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165945"
---
# <a name="relativesource-markupextension"></a><span data-ttu-id="61e8e-103">Extensión de marcado RelativeSource</span><span class="sxs-lookup"><span data-stu-id="61e8e-103">RelativeSource MarkupExtension</span></span>

<span data-ttu-id="61e8e-104">Especifica las propiedades de un <xref:System.Windows.Data.RelativeSource> origen de enlace, que se va a utilizar dentro de una [extensión de marcado de enlace](binding-markup-extension.md)o cuando se establece la <xref:System.Windows.Data.Binding.RelativeSource%2A> propiedad de un <xref:System.Windows.Data.Binding> elemento establecido en XAML.</span><span class="sxs-lookup"><span data-stu-id="61e8e-104">Specifies properties of a <xref:System.Windows.Data.RelativeSource> binding source, to be used within a [Binding Markup Extension](binding-markup-extension.md), or when setting the <xref:System.Windows.Data.Binding.RelativeSource%2A> property of a <xref:System.Windows.Data.Binding> element established in XAML.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="61e8e-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="61e8e-105">XAML Attribute Usage</span></span>

```xml
<Binding RelativeSource="{RelativeSource modeEnumValue}" ... />
```

## <a name="xaml-attribute-usage-nested-within-binding-extension"></a><span data-ttu-id="61e8e-106">Uso de atributos XAML (anidados en la extensión de enlace)</span><span class="sxs-lookup"><span data-stu-id="61e8e-106">XAML Attribute Usage (nested within Binding extension)</span></span>

```xml
<object property="{Binding RelativeSource={RelativeSource modeEnumValue} ...}" ... />
```

## <a name="xaml-object-element-usage"></a><span data-ttu-id="61e8e-107">Uso de elementos de objeto XAML</span><span class="sxs-lookup"><span data-stu-id="61e8e-107">XAML Object Element Usage</span></span>

```xml
<Binding>
  <Binding.RelativeSource>
    <RelativeSource Mode="modeEnumValue"/>
  </Binding.RelativeSource>
</Binding>
```

<span data-ttu-id="61e8e-108">O bien</span><span class="sxs-lookup"><span data-stu-id="61e8e-108">-or-</span></span>

```xml
<Binding>
  <Binding.RelativeSource>
    <RelativeSource
      Mode="FindAncestor"
      AncestorType="{x:Type typeName}"
      AncestorLevel="intLevel"
    />
  </Binding.RelativeSource>
</Binding>
```

## <a name="xaml-values"></a><span data-ttu-id="61e8e-109">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="61e8e-109">XAML Values</span></span>

|||
|-|-|
|`modeEnumValue`|<span data-ttu-id="61e8e-110">Uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="61e8e-110">One of the following:</span></span><br /><br /> <span data-ttu-id="61e8e-111">: El token de cadena `Self` ; corresponde a un <xref:System.Windows.Data.RelativeSource> tal como se creó con su <xref:System.Windows.Data.RelativeSource.Mode%2A> propiedad establecida en <xref:System.Windows.Data.RelativeSourceMode.Self> .</span><span class="sxs-lookup"><span data-stu-id="61e8e-111">-   The string token `Self`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.Self>.</span></span><br /><span data-ttu-id="61e8e-112">: El token de cadena `TemplatedParent` ; corresponde a un <xref:System.Windows.Data.RelativeSource> tal como se creó con su <xref:System.Windows.Data.RelativeSource.Mode%2A> propiedad establecida en <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent> .</span><span class="sxs-lookup"><span data-stu-id="61e8e-112">-   The string token `TemplatedParent`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>.</span></span><br /><span data-ttu-id="61e8e-113">: El token de cadena `PreviousData` ; corresponde a un <xref:System.Windows.Data.RelativeSource> tal como se creó con su <xref:System.Windows.Data.RelativeSource.Mode%2A> propiedad establecida en <xref:System.Windows.Data.RelativeSourceMode.PreviousData> .</span><span class="sxs-lookup"><span data-stu-id="61e8e-113">-   The string token `PreviousData`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.PreviousData>.</span></span><br /><span data-ttu-id="61e8e-114">-Consulte a continuación para obtener información sobre el `FindAncestor` modo.</span><span class="sxs-lookup"><span data-stu-id="61e8e-114">-   See below for information on `FindAncestor` mode.</span></span>|
|`FindAncestor`|<span data-ttu-id="61e8e-115">El token de cadena `FindAncestor`.</span><span class="sxs-lookup"><span data-stu-id="61e8e-115">The string token `FindAncestor`.</span></span> <span data-ttu-id="61e8e-116">Al utilizar este token, se entra en un modo en que `RelativeSource` especifica un tipo de antecesor y, opcionalmente, un nivel del antecesor.</span><span class="sxs-lookup"><span data-stu-id="61e8e-116">Using this token enters a mode whereby a `RelativeSource` specifies an ancestor type and optionally an ancestor level.</span></span> <span data-ttu-id="61e8e-117">Corresponde a un <xref:System.Windows.Data.RelativeSource> creado con su propiedad <xref:System.Windows.Data.RelativeSource.Mode%2A> establecida en <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.</span><span class="sxs-lookup"><span data-stu-id="61e8e-117">This corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.</span></span>|
|`typeName`|<span data-ttu-id="61e8e-118">Necesario para el modo `FindAncestor`.</span><span class="sxs-lookup"><span data-stu-id="61e8e-118">Required for `FindAncestor` mode.</span></span> <span data-ttu-id="61e8e-119">El nombre de un tipo, que rellena la propiedad <xref:System.Windows.Data.RelativeSource.AncestorType%2A>.</span><span class="sxs-lookup"><span data-stu-id="61e8e-119">The name of a type, which fills the <xref:System.Windows.Data.RelativeSource.AncestorType%2A> property.</span></span>|
|`intLevel`|<span data-ttu-id="61e8e-120">Opcional para el modo `FindAncestor`.</span><span class="sxs-lookup"><span data-stu-id="61e8e-120">Optional for `FindAncestor` mode.</span></span> <span data-ttu-id="61e8e-121">Un nivel del antecesor (se evalúa en la dirección del elemento primario en el árbol lógico).</span><span class="sxs-lookup"><span data-stu-id="61e8e-121">An ancestor level (evaluated towards the parent direction in the logical tree).</span></span>|

## <a name="remarks"></a><span data-ttu-id="61e8e-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="61e8e-122">Remarks</span></span>

<span data-ttu-id="61e8e-123">`{RelativeSource TemplatedParent}`los usos de enlace son una técnica clave que aborda un concepto más grande de la separación de la interfaz de usuario de un control y la lógica de un control.</span><span class="sxs-lookup"><span data-stu-id="61e8e-123">`{RelativeSource TemplatedParent}` binding usages are a key technique that addresses a larger concept of the separation of a control's UI and a control's logic.</span></span> <span data-ttu-id="61e8e-124">Esto permite enlazar desde dentro de la definición de plantilla al elemento primario con plantilla (instancia de objeto en tiempo de ejecución donde se aplica la plantilla).</span><span class="sxs-lookup"><span data-stu-id="61e8e-124">This enables binding from within the template definition to the templated parent (the run time object instance where the template is applied).</span></span> <span data-ttu-id="61e8e-125">En este caso, la [extensión de marcado TemplateBinding](templatebinding-markup-extension.md) es en realidad una abreviatura para la siguiente expresión de enlace: `{Binding RelativeSource={RelativeSource TemplatedParent}}` .</span><span class="sxs-lookup"><span data-stu-id="61e8e-125">For this case, the [TemplateBinding Markup Extension](templatebinding-markup-extension.md) is in fact a shorthand for the following binding expression: `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span></span> <span data-ttu-id="61e8e-126">`TemplateBinding`los `{RelativeSource TemplatedParent}` usos de o solo son relevantes en el código XAML que define una plantilla.</span><span class="sxs-lookup"><span data-stu-id="61e8e-126">`TemplateBinding` or `{RelativeSource TemplatedParent}` usages are both only relevant within the XAML that defines a template.</span></span> <span data-ttu-id="61e8e-127">Para obtener más información, consulte [extensión de marcado TemplateBinding](templatebinding-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="61e8e-127">For more information, see [TemplateBinding Markup Extension](templatebinding-markup-extension.md).</span></span>

<span data-ttu-id="61e8e-128">`{RelativeSource FindAncestor}`se usa principalmente en las plantillas de control o en las composiciones de interfaz de usuario independientes de predicción, en los casos en los que siempre se espera que un control esté en un árbol visual de un tipo de antecesor determinado.</span><span class="sxs-lookup"><span data-stu-id="61e8e-128">`{RelativeSource FindAncestor}` is mainly used in control templates or predictable self-contained UI compositions, for cases where a control is always expected to be in a visual tree of a certain ancestor type.</span></span> <span data-ttu-id="61e8e-129">Por ejemplo, los elementos de un control de elementos pueden usar `FindAncestor` para enlazar a propiedades del antecesor del elemento primario del control de elementos.</span><span class="sxs-lookup"><span data-stu-id="61e8e-129">For example, items of an items control might use `FindAncestor` usages to bind to properties of their items control parent ancestor.</span></span> <span data-ttu-id="61e8e-130">O bien los elementos que forman parte de la composición de controles en una plantilla pueden usar enlaces `FindAncestor` a los elementos primarios en esa misma estructura de composición.</span><span class="sxs-lookup"><span data-stu-id="61e8e-130">Or, elements that are part of control composition in a template can use `FindAncestor` bindings to the parent elements in that same composition structure.</span></span>

<span data-ttu-id="61e8e-131">En la sintaxis de elementos de objeto para el modo `FindAncestor` que se muestra en las secciones sobre sintaxis XAML, la segunda sintaxis de elementos de objeto se emplea específicamente para el modo `FindAncestor`.</span><span class="sxs-lookup"><span data-stu-id="61e8e-131">In the object element syntax for `FindAncestor` mode shown in the XAML Syntax sections, the second object element syntax is used specifically for `FindAncestor` mode.</span></span> <span data-ttu-id="61e8e-132">El modo `FindAncestor` necesita un valor de <xref:System.Windows.Data.RelativeSource.AncestorType%2A>.</span><span class="sxs-lookup"><span data-stu-id="61e8e-132">`FindAncestor` mode requires an <xref:System.Windows.Data.RelativeSource.AncestorType%2A> value.</span></span> <span data-ttu-id="61e8e-133">Debe establecer <xref:System.Windows.Data.RelativeSource.AncestorType%2A> como un atributo mediante una referencia de [extensión de marcado x:Type](../../../desktop-wpf/xaml-services/xtype-markup-extension.md) al tipo de antecesor que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="61e8e-133">You must set <xref:System.Windows.Data.RelativeSource.AncestorType%2A> as an attribute using an [x:Type Markup Extension](../../../desktop-wpf/xaml-services/xtype-markup-extension.md) reference to the type of ancestor to look for.</span></span> <span data-ttu-id="61e8e-134">Se utiliza el valor de <xref:System.Windows.Data.RelativeSource.AncestorType%2A> al procesar la solicitud de enlace en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="61e8e-134">The <xref:System.Windows.Data.RelativeSource.AncestorType%2A> value is used when the binding request is processed at run-time.</span></span>

<span data-ttu-id="61e8e-135">Para el modo `FindAncestor`, la propiedad <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> opcional puede ayudar a eliminar la ambigüedad en la búsqueda del antecesor en aquellos casos en que sea posible que exista más de un antecesor de ese tipo en el árbol de elementos.</span><span class="sxs-lookup"><span data-stu-id="61e8e-135">For `FindAncestor` mode, the optional property <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> can help disambiguate the ancestor lookup in cases where there is possibly more than one ancestor of that type existing in the element tree.</span></span>

<span data-ttu-id="61e8e-136">Para obtener más información sobre cómo usar el modo `FindAncestor`, vea <xref:System.Windows.Data.RelativeSource>.</span><span class="sxs-lookup"><span data-stu-id="61e8e-136">For more information on how to use the `FindAncestor` mode, see <xref:System.Windows.Data.RelativeSource>.</span></span>

<span data-ttu-id="61e8e-137">`{RelativeSource Self}`resulta útil para escenarios en los que una propiedad de una instancia debe depender del valor de otra propiedad de la misma instancia, y no existe ninguna relación de propiedad de dependencia general (como la coerción) entre esas dos propiedades.</span><span class="sxs-lookup"><span data-stu-id="61e8e-137">`{RelativeSource Self}` is useful for scenarios where one property of an instance should depend on the value of another property of the same instance, and no general dependency property relationship (such as coercion) already exists between those two properties.</span></span> <span data-ttu-id="61e8e-138">Aunque es poco frecuente que existan dos propiedades en un objeto de modo que los valores sean literalmente idénticos (y tengan tipos idénticos), también puede aplicar un `Converter` parámetro a un enlace que tenga `{RelativeSource Self}` y usar el convertidor para realizar la conversión entre los tipos de origen y de destino.</span><span class="sxs-lookup"><span data-stu-id="61e8e-138">Although it is rare that two properties exist on an object such that the values are literally identical (and are identically typed), you can also apply a `Converter` parameter to a binding that has `{RelativeSource Self}`, and use the converter to convert between source and target types.</span></span> <span data-ttu-id="61e8e-139">Otro escenario para `{RelativeSource Self}` es como parte de un <xref:System.Windows.MultiDataTrigger> .</span><span class="sxs-lookup"><span data-stu-id="61e8e-139">Another scenario for `{RelativeSource Self}` is as part of a <xref:System.Windows.MultiDataTrigger>.</span></span>

<span data-ttu-id="61e8e-140">Por ejemplo, el código XAML siguiente define un elemento <xref:System.Windows.Shapes.Rectangle> de forma que, independientemente del valor que se especifique para <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.Shapes.Rectangle> sea siempre un cuadrado: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`</span><span class="sxs-lookup"><span data-stu-id="61e8e-140">For example, the following XAML defines a <xref:System.Windows.Shapes.Rectangle> element such that no matter what value is entered for <xref:System.Windows.FrameworkElement.Width%2A>, the <xref:System.Windows.Shapes.Rectangle> is always a square: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`</span></span>

<span data-ttu-id="61e8e-141">`{RelativeSource PreviousData}`es útil en las plantillas de datos o en los casos en los que los enlaces utilizan una colección como origen de datos.</span><span class="sxs-lookup"><span data-stu-id="61e8e-141">`{RelativeSource PreviousData}` is useful either in data templates, or in cases where bindings are using a collection as the data source.</span></span> <span data-ttu-id="61e8e-142">Puede usar `{RelativeSource PreviousData}` para resaltar las relaciones entre los elementos de datos adyacentes de la colección.</span><span class="sxs-lookup"><span data-stu-id="61e8e-142">You can use `{RelativeSource PreviousData}` to highlight relationships between adjacent data items in the collection.</span></span> <span data-ttu-id="61e8e-143">Una técnica relacionada es establecer un objeto <xref:System.Windows.Data.MultiBinding> entre los elementos actual y anterior del origen de datos, y utilizar un convertidor en dicho enlace para determinar la diferencia entre ambos elementos y sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="61e8e-143">A related technique is to establish a <xref:System.Windows.Data.MultiBinding> between the current and previous items in the data source, and use a converter on that binding to determine the difference between the two items and their properties.</span></span>

<span data-ttu-id="61e8e-144">En el ejemplo siguiente, el primer <xref:System.Windows.Controls.TextBlock> de la plantilla de elementos muestra el número actual.</span><span class="sxs-lookup"><span data-stu-id="61e8e-144">In the following example, the first <xref:System.Windows.Controls.TextBlock> in the items template displays the current number.</span></span> <span data-ttu-id="61e8e-145">El segundo <xref:System.Windows.Controls.TextBlock> enlace es un <xref:System.Windows.Data.MultiBinding> que tiene nominalmente dos <xref:System.Windows.Data.Binding> componentes: el registro actual y un enlace que usa deliberadamente el registro de datos anterior mediante `{RelativeSource PreviousData}` .</span><span class="sxs-lookup"><span data-stu-id="61e8e-145">The second <xref:System.Windows.Controls.TextBlock> binding is a <xref:System.Windows.Data.MultiBinding> that nominally has two <xref:System.Windows.Data.Binding> constituents: the current record, and a binding that deliberately uses the previous data record by using `{RelativeSource PreviousData}`.</span></span> <span data-ttu-id="61e8e-146">A continuación, un convertidor en el objeto <xref:System.Windows.Data.MultiBinding> calcula la diferencia y la devuelve al enlace.</span><span class="sxs-lookup"><span data-stu-id="61e8e-146">Then, a converter on the <xref:System.Windows.Data.MultiBinding> calculates the difference and returns it to the binding.</span></span>

```xml
<ListBox Name="fibolist">
    <ListBox.ItemTemplate>
        <DataTemplate>
            <StackPanel Orientation="Horizontal">
            <TextBlock Text="{Binding}"/>
            <TextBlock>, difference = </TextBlock>
                <TextBlock>
                    <TextBlock.Text>
                        <MultiBinding Converter="{StaticResource DiffConverter}">
                            <Binding/>
                            <Binding RelativeSource="{RelativeSource PreviousData}"/>
                        </MultiBinding>
                    </TextBlock.Text>
                </TextBlock>
            </StackPanel>
        </DataTemplate>
    </ListBox.ItemTemplate>
</ListBox>
```

<span data-ttu-id="61e8e-147">La descripción de los enlaces de datos como concepto no se trata aquí, vea [información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="61e8e-147">Describing data binding as a concept is not covered here, see [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

<span data-ttu-id="61e8e-148">En la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementación del procesador XAML, la clase define el control para esta extensión de marcado <xref:System.Windows.Data.RelativeSource> .</span><span class="sxs-lookup"><span data-stu-id="61e8e-148">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.Data.RelativeSource> class.</span></span>

<span data-ttu-id="61e8e-149">`RelativeSource` es una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="61e8e-149">`RelativeSource` is a markup extension.</span></span> <span data-ttu-id="61e8e-150">Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades.</span><span class="sxs-lookup"><span data-stu-id="61e8e-150">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="61e8e-151">Todas las extensiones de marcado de XAML usan los `{` `}` caracteres y en su sintaxis de atributo, que es la Convención por la que un procesador XAML reconoce que una extensión de marcado debe procesar el atributo.</span><span class="sxs-lookup"><span data-stu-id="61e8e-151">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="61e8e-152">Para más información, vea [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="61e8e-152">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="61e8e-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="61e8e-153">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="61e8e-154">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="61e8e-154">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="61e8e-155">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="61e8e-155">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="61e8e-156">Extensiones de marcado y XAML de WPF</span><span class="sxs-lookup"><span data-stu-id="61e8e-156">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="61e8e-157">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="61e8e-157">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="61e8e-158">Información general sobre declaraciones de enlaces</span><span class="sxs-lookup"><span data-stu-id="61e8e-158">Binding Declarations Overview</span></span>](../data/binding-declarations-overview.md)
- [<span data-ttu-id="61e8e-159">x:Type (extensión de marcado)</span><span class="sxs-lookup"><span data-stu-id="61e8e-159">x:Type Markup Extension</span></span>](../../../desktop-wpf/xaml-services/xtype-markup-extension.md)
