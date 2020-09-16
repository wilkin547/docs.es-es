---
title: x:TypeArguments (Directiva)
ms.date: 03/30/2017
f1_keywords:
- x:TypeArguments
- xTypeArguments
- TypeArguments
helpviewer_keywords:
- x:TypeArguments attribute [XAML Services]
- TypeArguments attribute in XAML [XAML Services]
- XAML [XAML Services], x:TypeArguments attribute
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
ms.openlocfilehash: 430ab65af52282ccb1d429cd2523efe213f13609
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543556"
---
# <a name="xtypearguments-directive"></a><span data-ttu-id="f8faa-102">x:TypeArguments (Directiva)</span><span class="sxs-lookup"><span data-stu-id="f8faa-102">x:TypeArguments Directive</span></span>

<span data-ttu-id="f8faa-103">Pasa los argumentos de tipo restrictivos de un genérico al constructor del tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="f8faa-103">Passes constraining type arguments of a generic to the constructor of the generic type.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="f8faa-104">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="f8faa-104">XAML Attribute Usage</span></span>

```xaml
<object x:TypeArguments="typeString" .../>
```

## <a name="xaml-values"></a><span data-ttu-id="f8faa-105">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="f8faa-105">XAML Values</span></span>

|||
|-|-|
|`object`|<span data-ttu-id="f8faa-106">Una declaración de elemento de objeto de un tipo XAML, que está respaldada por un tipo genérico de CLR.</span><span class="sxs-lookup"><span data-stu-id="f8faa-106">An object element declaration of a XAML type, which is backed by a CLR generic type.</span></span> <span data-ttu-id="f8faa-107">Si `object` hace referencia a un tipo XAML que no es del espacio de nombres XAML predeterminado, `object` requiere un prefijo para indicar el espacio de nombres XAML donde `object` existe.</span><span class="sxs-lookup"><span data-stu-id="f8faa-107">If `object` refers to a XAML type that is not from the default XAML namespace, `object` requires a prefix to indicate the XAML namespace where `object` exists.</span></span>|
|`typeString`|<span data-ttu-id="f8faa-108">Cadena que declara uno o más nombres de tipo XAML como cadenas, lo que proporciona los argumentos de tipo para el tipo genérico de CLR.</span><span class="sxs-lookup"><span data-stu-id="f8faa-108">A string that declares one or more XAML type names as strings, which supplies the type arguments for the CLR generic type.</span></span> <span data-ttu-id="f8faa-109">Vea la sección Comentarios para obtener más notas sobre la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="f8faa-109">See Remarks for additional syntax notes.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f8faa-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f8faa-110">Remarks</span></span>

<span data-ttu-id="f8faa-111">En la mayoría de los casos, los tipos XAML que se usan como un elemento de información en una `typeString` cadena tienen el prefijo.</span><span class="sxs-lookup"><span data-stu-id="f8faa-111">In most cases, the XAML types that are used as an information item in a `typeString` string are prefixed.</span></span> <span data-ttu-id="f8faa-112">Los tipos típicos de restricciones genéricas de CLR (por ejemplo, <xref:System.Int32> y <xref:System.String> ) proceden de las bibliotecas de clases base de CLR.</span><span class="sxs-lookup"><span data-stu-id="f8faa-112">Typical types of CLR generic constraints (for example, <xref:System.Int32> and <xref:System.String>) come from CLR base class libraries.</span></span> <span data-ttu-id="f8faa-113">Estas bibliotecas no se asignan a los espacios de nombres XAML predeterminados específicos del marco y, por lo tanto, requieren una asignación de prefijo para el uso de XAML.</span><span class="sxs-lookup"><span data-stu-id="f8faa-113">Those libraries are not mapped to typical framework-specific default XAML namespaces, and therefore, require a prefix mapping for XAML usage.</span></span>

<span data-ttu-id="f8faa-114">Puede especificar más de un nombre de tipo XAML mediante un delimitador de coma.</span><span class="sxs-lookup"><span data-stu-id="f8faa-114">You can specify more than one XAML type name by using a comma delimiter.</span></span>

<span data-ttu-id="f8faa-115">Si las restricciones genéricas usan tipos genéricos, los argumentos de tipo de restricción anidados pueden estar incluidos entre paréntesis ().</span><span class="sxs-lookup"><span data-stu-id="f8faa-115">If the generic constraints themselves use generic types, the nested constraint type arguments can be contained by parentheses ().</span></span>

<span data-ttu-id="f8faa-116">Tenga en cuenta que esta definición de `x:TypeArguments` es específica de los servicios XAML de .net y usa la copia de seguridad de CLR.</span><span class="sxs-lookup"><span data-stu-id="f8faa-116">Note that this definition of `x:TypeArguments` is specific to .NET XAML Services and using CLR backing.</span></span> <span data-ttu-id="f8faa-117">Puede encontrar una definición de nivel de lenguaje en la [ \[ sección MS-XAML \] 5.3.11](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="f8faa-117">A language-level definition can be found in [\[MS-XAML\] Section 5.3.11](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

## <a name="usage-examples"></a><span data-ttu-id="f8faa-118">Ejemplos de uso</span><span class="sxs-lookup"><span data-stu-id="f8faa-118">Usage Examples</span></span>

<span data-ttu-id="f8faa-119">En estos ejemplos, suponga que se declaran las siguientes definiciones de espacio de nombres XAML:</span><span class="sxs-lookup"><span data-stu-id="f8faa-119">For these examples, assume that the following XAML namespace definitions are declared:</span></span>

```xaml
xmlns:sys="clr-namespace:System;assembly=mscorlib"
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"
```

### <a name="liststring"></a><span data-ttu-id="f8faa-120">List\<String></span><span class="sxs-lookup"><span data-stu-id="f8faa-120">List\<String></span></span>

<span data-ttu-id="f8faa-121">`<scg:List x:TypeArguments="sys:String" ...>` crea una instancia de un nuevo <xref:System.Collections.Generic.List%601> con un <xref:System.String> argumento de tipo.</span><span class="sxs-lookup"><span data-stu-id="f8faa-121">`<scg:List x:TypeArguments="sys:String" ...>` instantiates a new <xref:System.Collections.Generic.List%601> with a <xref:System.String> type argument.</span></span>

### <a name="dictionarystringstring"></a><span data-ttu-id="f8faa-122">Diccionario\<String,String></span><span class="sxs-lookup"><span data-stu-id="f8faa-122">Dictionary\<String,String></span></span>

<span data-ttu-id="f8faa-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` crea una instancia de un nuevo <xref:System.Collections.Generic.Dictionary%602> con dos <xref:System.String> argumentos de tipo.</span><span class="sxs-lookup"><span data-stu-id="f8faa-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instantiates a new <xref:System.Collections.Generic.Dictionary%602> with two <xref:System.String> type arguments.</span></span>

### <a name="queuekeyvaluepairstringstring"></a><span data-ttu-id="f8faa-124"><de la cola KeyValuePair\<String,String>></span><span class="sxs-lookup"><span data-stu-id="f8faa-124">Queue<KeyValuePair\<String,String>></span></span>

<span data-ttu-id="f8faa-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` crea una instancia de un nuevo <xref:System.Collections.Generic.Queue%601> que tiene una restricción de <xref:System.Collections.Generic.KeyValuePair%602> con los argumentos de tipo de restricción interna <xref:System.String> y <xref:System.String> .</span><span class="sxs-lookup"><span data-stu-id="f8faa-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instantiates a new <xref:System.Collections.Generic.Queue%601> that has a constraint of <xref:System.Collections.Generic.KeyValuePair%602> with the inner constraint type arguments <xref:System.String> and <xref:System.String>.</span></span>

## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a><span data-ttu-id="f8faa-126">XAML 2006 y usos de XAML genéricos de WPF</span><span class="sxs-lookup"><span data-stu-id="f8faa-126">XAML 2006 and WPF Generic XAML Usages</span></span>

<span data-ttu-id="f8faa-127">Para el uso de XAML 2006 y el XAML que se usa para las aplicaciones de WPF, existen las siguientes restricciones para los `x:TypeArguments` usos de tipos genéricos de XAML en general:</span><span class="sxs-lookup"><span data-stu-id="f8faa-127">For XAML 2006 usage, and XAML that is used for WPF applications, the following restrictions exist for `x:TypeArguments` and generic type usages from XAML in general:</span></span>

- <span data-ttu-id="f8faa-128">Solo el elemento raíz de un archivo XAML puede admitir un uso de XAML genérico que hace referencia a un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="f8faa-128">Only the root element of a XAML file can support a generic XAML usage that references a generic type.</span></span>

- <span data-ttu-id="f8faa-129">El elemento raíz debe asignarse a un tipo genérico con al menos un argumento de tipo.</span><span class="sxs-lookup"><span data-stu-id="f8faa-129">The root element must map to a generic type with at least one type argument.</span></span> <span data-ttu-id="f8faa-130">Un ejemplo es <xref:System.Windows.Navigation.PageFunction%601>.</span><span class="sxs-lookup"><span data-stu-id="f8faa-130">An example is <xref:System.Windows.Navigation.PageFunction%601>.</span></span> <span data-ttu-id="f8faa-131">Las funciones de página son el escenario principal para la compatibilidad con el uso genérico de XAML en WPF.</span><span class="sxs-lookup"><span data-stu-id="f8faa-131">The page functions are the primary scenario for XAML generic usage support in WPF.</span></span>

- <span data-ttu-id="f8faa-132">El elemento raíz del elemento de objeto XAML para el genérico también debe declarar una clase parcial mediante `x:Class` .</span><span class="sxs-lookup"><span data-stu-id="f8faa-132">The root element XAML object element for the generic must also declare a partial class using `x:Class`.</span></span> <span data-ttu-id="f8faa-133">Esto es así incluso si se define una acción de compilación de WPF.</span><span class="sxs-lookup"><span data-stu-id="f8faa-133">This is true even if defining a WPF build action.</span></span>

- <span data-ttu-id="f8faa-134">`x:TypeArguments` no se puede hacer referencia a restricciones genéricas anidadas.</span><span class="sxs-lookup"><span data-stu-id="f8faa-134">`x:TypeArguments` cannot reference nested generic constraints.</span></span>

## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a><span data-ttu-id="f8faa-135">XAML 2009 o XAML 2006 sin dependencia de WPF 3,0 o WPF 3,5</span><span class="sxs-lookup"><span data-stu-id="f8faa-135">XAML 2009 or XAML 2006 with No WPF 3.0 or WPF 3.5 Dependency</span></span>

<span data-ttu-id="f8faa-136">En los servicios XAML de .NET para XAML 2006 o XAML 2009, se relajan las restricciones relacionadas con WPF en el uso de XAML genérico.</span><span class="sxs-lookup"><span data-stu-id="f8faa-136">In .NET XAML Services for either XAML 2006 or XAML 2009, the WPF-related restrictions on generic XAML usage are relaxed.</span></span> <span data-ttu-id="f8faa-137">Puede crear instancias de un elemento de objeto genérico en cualquier posición en el marcado XAML que admitan el sistema de tipos de respaldo y el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="f8faa-137">You can instantiate a generic object element at any position in XAML markup that the backing type system and object model can support.</span></span>

<span data-ttu-id="f8faa-138">Si usa XAML 2009 en lugar de asignar los tipos base de CLR para obtener tipos XAML para los primitivos del lenguaje común, puede usar [tipos integrados para primitivas del lenguaje XAML comunes](types-for-primitives.md) como elementos de información en un `typeString` .</span><span class="sxs-lookup"><span data-stu-id="f8faa-138">If you use XAML 2009 instead of mapping the CLR base types to obtain XAML types for common language primitives, you can use [Built-in Types for Common XAML Language Primitives](types-for-primitives.md) as information items in a `typeString`.</span></span> <span data-ttu-id="f8faa-139">Por ejemplo, podría declarar lo siguiente (no se muestran las asignaciones de prefijo, pero x es el espacio de nombres XAML del lenguaje XAML para XAML 2009):</span><span class="sxs-lookup"><span data-stu-id="f8faa-139">For example, you could declare the following (prefix mappings not shown, but x is the XAML language XAML namespace for XAML 2009):</span></span>

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

<span data-ttu-id="f8faa-140">En WPF y cuando el destino es .NET Framework 4 o .NET Core 3,0 (o posterior), puede usar las características de XAML 2009 junto con `x:TypeArguments` pero solo para XAML dinámico (XAML que no está compilado por marcado).</span><span class="sxs-lookup"><span data-stu-id="f8faa-140">In WPF and when targeting .NET Framework 4 or .NET Core 3.0 (or later), you can use XAML 2009 features together with `x:TypeArguments` but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="f8faa-141">XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento las palabras clave y características de XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="f8faa-141">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span> <span data-ttu-id="f8faa-142">Si necesita marcado compilar el código XAML, debe operar con las restricciones que se indican en la sección [xaml 2006 y los usos de XAML genéricos de WPF](#xaml-2006-and-wpf-generic-xaml-usages) .</span><span class="sxs-lookup"><span data-stu-id="f8faa-142">If you need to markup compile the XAML, you must operate under the restrictions noted in the [XAML 2006 and WPF Generic XAML Usages](#xaml-2006-and-wpf-generic-xaml-usages) section.</span></span> <span data-ttu-id="f8faa-143">BAML solo se admite en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f8faa-143">BAML is only supported in .NET Framework.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8faa-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8faa-144">See also</span></span>

- [<span data-ttu-id="f8faa-145">x:Class (Directiva)</span><span class="sxs-lookup"><span data-stu-id="f8faa-145">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="f8faa-146">x:Type (Extensión de marcado)</span><span class="sxs-lookup"><span data-stu-id="f8faa-146">x:Type Markup Extension</span></span>](xtype-markup-extension.md)
- [<span data-ttu-id="f8faa-147">Tipos integrados para primitivas comunes en el lenguaje XAML</span><span class="sxs-lookup"><span data-stu-id="f8faa-147">Built-in Types for Common XAML Language Primitives</span></span>](types-for-primitives.md)
- [<span data-ttu-id="f8faa-148">Elementos genéricos en XAML</span><span class="sxs-lookup"><span data-stu-id="f8faa-148">Generics in XAML</span></span>](generics.md)
