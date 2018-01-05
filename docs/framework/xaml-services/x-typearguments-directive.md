---
title: x:TypeArguments (Directiva)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:TypeArguments
- xTypeArguments
- TypeArguments
helpviewer_keywords:
- x:TypeArguments attribute [XAML Services]
- TypeArguments attribute in XAML [XAML Services]
- XAML [XAML Services], x:TypeArguments attribute
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
caps.latest.revision: "18"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e601fb5895460e52aa21836c542d0b1367527f09
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="xtypearguments-directive"></a><span data-ttu-id="17fe0-102">x:TypeArguments (Directiva)</span><span class="sxs-lookup"><span data-stu-id="17fe0-102">x:TypeArguments Directive</span></span>
<span data-ttu-id="17fe0-103">Pasa al restringir los argumentos de un tipo genérico para el constructor del tipo genérico de tipo.</span><span class="sxs-lookup"><span data-stu-id="17fe0-103">Passes constraining type arguments of a generic to the constructor of the generic type.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="17fe0-104">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="17fe0-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:TypeArguments="typeString" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="17fe0-105">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="17fe0-105">XAML Values</span></span>  
  
|||  
|-|-|  
|`object`|<span data-ttu-id="17fe0-106">Una declaración de elemento de objeto de un tipo XAML, que está respaldado por un tipo genérico de CLR.</span><span class="sxs-lookup"><span data-stu-id="17fe0-106">An object element declaration of a XAML type, which is backed by a CLR generic type.</span></span> <span data-ttu-id="17fe0-107">Si `object` hace referencia a un tipo XAML que no esté en el espacio de nombres XAML predeterminado, `object` requiere un prefijo para indicar el espacio de nombres XAML donde `object` existe.</span><span class="sxs-lookup"><span data-stu-id="17fe0-107">If `object` refers to a XAML type that is not from the default XAML namespace, `object` requires a prefix to indicate the XAML namespace where `object` exists.</span></span>|  
|`typeString`|<span data-ttu-id="17fe0-108">Una cadena que declara uno o más XAML escriba nombres como cadenas, lo que proporciona los argumentos de tipo para el tipo genérico de CLR.</span><span class="sxs-lookup"><span data-stu-id="17fe0-108">A string that declares one or more XAML type names as strings, which supplies the type arguments for the CLR generic type.</span></span> <span data-ttu-id="17fe0-109">Vea la sección Comentarios para obtener notas adicionales de la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="17fe0-109">See Remarks for additional syntax notes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17fe0-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="17fe0-110">Remarks</span></span>  
 <span data-ttu-id="17fe0-111">En la mayoría de los casos, los tipos XAML que se usan como un elemento de información en un `typeString` cadena tienen el prefijo.</span><span class="sxs-lookup"><span data-stu-id="17fe0-111">In most cases, the XAML types that are used as an information item in a `typeString` string are prefixed.</span></span> <span data-ttu-id="17fe0-112">Los tipos típicos de restricciones genéricas de CLR (por ejemplo, <xref:System.Int32> y <xref:System.String>) proceden de bibliotecas de clases base de CLR.</span><span class="sxs-lookup"><span data-stu-id="17fe0-112">Typical types of CLR generic constraints (for example, <xref:System.Int32> and <xref:System.String>) come from CLR base class libraries.</span></span> <span data-ttu-id="17fe0-113">Esas bibliotecas no están asignadas a típica predeterminada específica del marco espacios de nombres XAML y, por lo tanto, requieren una asignación de prefijo para el uso XAML.</span><span class="sxs-lookup"><span data-stu-id="17fe0-113">Those libraries are not mapped to typical framework-specific default XAML namespaces, and therefore, require a prefix mapping for XAML usage.</span></span>  
  
 <span data-ttu-id="17fe0-114">Puede especificar más de un nombre de tipo XAML mediante un delimitador de coma.</span><span class="sxs-lookup"><span data-stu-id="17fe0-114">You can specify more than one XAML type name by using a comma delimiter.</span></span>  
  
 <span data-ttu-id="17fe0-115">Si las propias restricciones genéricas usan tipos genéricos, los argumentos de tipo de restricción anidados pueden estar contenidos en paréntesis ().</span><span class="sxs-lookup"><span data-stu-id="17fe0-115">If the generic constraints themselves use generic types, the nested constraint type arguments can be contained by parentheses ().</span></span>  
  
 <span data-ttu-id="17fe0-116">Tenga en cuenta que esta definición de `x:TypeArguments` es específica a los servicios XAML de .NET Framework y utilizar copias de seguridad de CLR.</span><span class="sxs-lookup"><span data-stu-id="17fe0-116">Note that this definition of `x:TypeArguments` is specific to .NET Framework XAML Services and using CLR backing.</span></span> <span data-ttu-id="17fe0-117">Una definición de nivel de lenguaje se puede encontrar en [ \[MS-XAML\] sección 5.3.11](http://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="17fe0-117">A language-level definition can be found in [\[MS-XAML\] Section 5.3.11](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="usage-examples"></a><span data-ttu-id="17fe0-118">Ejemplos de uso</span><span class="sxs-lookup"><span data-stu-id="17fe0-118">Usage Examples</span></span>  
 <span data-ttu-id="17fe0-119">Para estos ejemplos, se supone que se declaran las siguientes definiciones de espacio de nombres XAML:</span><span class="sxs-lookup"><span data-stu-id="17fe0-119">For these examples, assume that the following XAML namespace definitions are declared:</span></span>  
  
```  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a><span data-ttu-id="17fe0-120">Lista\<cadena ></span><span class="sxs-lookup"><span data-stu-id="17fe0-120">List\<String></span></span>  
 <span data-ttu-id="17fe0-121">`<scg:List x:TypeArguments="sys:String" ...>`crea una instancia de un nuevo <xref:System.Collections.Generic.List%601> con una <xref:System.String> el argumento de tipo.</span><span class="sxs-lookup"><span data-stu-id="17fe0-121">`<scg:List x:TypeArguments="sys:String" ...>` instantiates a new <xref:System.Collections.Generic.List%601> with a <xref:System.String> type argument.</span></span>  
  
### <a name="dictionarystringstring"></a><span data-ttu-id="17fe0-122">Diccionario\<cadena, cadena ></span><span class="sxs-lookup"><span data-stu-id="17fe0-122">Dictionary\<String,String></span></span>  
 <span data-ttu-id="17fe0-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>`crea una instancia de un nuevo <xref:System.Collections.Generic.Dictionary%602> con dos <xref:System.String> argumentos de tipo.</span><span class="sxs-lookup"><span data-stu-id="17fe0-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instantiates a new <xref:System.Collections.Generic.Dictionary%602> with two <xref:System.String> type arguments.</span></span>  
  
### <a name="queuekeyvaluepairstringstring"></a><span data-ttu-id="17fe0-124">Cola < KeyValuePair\<cadena, cadena >></span><span class="sxs-lookup"><span data-stu-id="17fe0-124">Queue<KeyValuePair\<String,String>></span></span>  
 <span data-ttu-id="17fe0-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>`crea una instancia de un nuevo <xref:System.Collections.Generic.Queue%601> que tiene una restricción de <xref:System.Collections.Generic.KeyValuePair%602> con los argumentos de tipo de restricción interna <xref:System.String> y <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="17fe0-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instantiates a new <xref:System.Collections.Generic.Queue%601> that has a constraint of <xref:System.Collections.Generic.KeyValuePair%602> with the inner constraint type arguments <xref:System.String> and <xref:System.String>.</span></span>  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a><span data-ttu-id="17fe0-126">Usos XAML genéricos de XAML 2006 y WPF</span><span class="sxs-lookup"><span data-stu-id="17fe0-126">XAML 2006 and WPF Generic XAML Usages</span></span>  
 <span data-ttu-id="17fe0-127">Para el uso de XAML 2006 y XAML que se usa para las aplicaciones WPF, existen las siguientes restricciones para `x:TypeArguments` y usos de tipo genérico de XAML en general:</span><span class="sxs-lookup"><span data-stu-id="17fe0-127">For XAML 2006 usage, and XAML that is used for WPF applications, the following restrictions exist for `x:TypeArguments` and generic type usages from XAML in general:</span></span>  
  
-   <span data-ttu-id="17fe0-128">Solo el elemento raíz de un archivo XAML puede admitir un uso XAML genérico que hace referencia a un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="17fe0-128">Only the root element of a XAML file can support a generic XAML usage that references a generic type.</span></span>  
  
-   <span data-ttu-id="17fe0-129">El elemento raíz debe asignar a un tipo genérico con al menos un argumento de tipo.</span><span class="sxs-lookup"><span data-stu-id="17fe0-129">The root element must map to a generic type with at least one type argument.</span></span> <span data-ttu-id="17fe0-130">Un ejemplo es <xref:System.Windows.Navigation.PageFunction%601>.</span><span class="sxs-lookup"><span data-stu-id="17fe0-130">An example is <xref:System.Windows.Navigation.PageFunction%601>.</span></span> <span data-ttu-id="17fe0-131">Las funciones de página son el escenario principal para la compatibilidad de uso genérico de XAML en WPF.</span><span class="sxs-lookup"><span data-stu-id="17fe0-131">The page functions are the primary scenario for XAML generic usage support in WPF.</span></span>  
  
-   <span data-ttu-id="17fe0-132">El elemento de objeto XAML de elemento raíz para el genérico también debe declarar una clase parcial con `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="17fe0-132">The root element XAML object element for the generic must also declare a partial class using `x:Class`.</span></span> <span data-ttu-id="17fe0-133">Esto es cierto incluso si la acción de compilación de definir un WPF.</span><span class="sxs-lookup"><span data-stu-id="17fe0-133">This is true even if defining a WPF build action.</span></span>  
  
-   <span data-ttu-id="17fe0-134">`x:TypeArguments`no se puede hacer referencia a las restricciones genéricas anidadas.</span><span class="sxs-lookup"><span data-stu-id="17fe0-134">`x:TypeArguments` cannot reference nested generic constraints.</span></span>  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a><span data-ttu-id="17fe0-135">XAML 2009 o XAML 2006 con ningún WPF 3.0 o 3.5 de WPF dependencia</span><span class="sxs-lookup"><span data-stu-id="17fe0-135">XAML 2009 or XAML 2006 with No WPF 3.0 or WPF 3.5 Dependency</span></span>  
 <span data-ttu-id="17fe0-136">En servicios de XAML de .NET Framework para XAML 2006 o XAML 2009, se relajan las restricciones relacionadas con WPF en el uso XAML genérico.</span><span class="sxs-lookup"><span data-stu-id="17fe0-136">In .NET Framework XAML Services for either XAML 2006 or XAML 2009, the WPF-related restrictions on generic XAML usage are relaxed.</span></span> <span data-ttu-id="17fe0-137">Puede crear una instancia de un elemento de objeto genérico en cualquier posición del marcado XAML que puede admitir el modelo de objeto y de sistema de tipos de respaldo.</span><span class="sxs-lookup"><span data-stu-id="17fe0-137">You can instantiate a generic object element at any position in XAML markup that the backing type system and object model can support.</span></span>  
  
 <span data-ttu-id="17fe0-138">Si utiliza XAML 2009 en lugar de asignar el CLR de tipos para obtener tipos XAML para los primitivos del lenguaje común base, puede usar [tipos integrados para primitivas del lenguaje XAML común](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) como elementos de información en un `typeString`.</span><span class="sxs-lookup"><span data-stu-id="17fe0-138">If you use XAML 2009 instead of mapping the CLR base types to obtain XAML types for common language primitives, you can use [Built-in Types for Common XAML Language Primitives](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) as information items in a `typeString`.</span></span> <span data-ttu-id="17fe0-139">Por ejemplo, podría declarar lo siguiente (asignaciones de prefijos no se muestran, pero x es el espacio de nombres XAML del lenguaje XAML para XAML 2009):</span><span class="sxs-lookup"><span data-stu-id="17fe0-139">For example, you could declare the following (prefix mappings not shown, but x is the XAML language XAML namespace for XAML 2009):</span></span>  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 <span data-ttu-id="17fe0-140">En WPF y cuando el destino es [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], puede usar las características de XAML 2009 junto con `x:TypeArguments` , pero solo para XAML dinámico (XAML que no está compilado por marcado).</span><span class="sxs-lookup"><span data-stu-id="17fe0-140">In WPF and when targeting [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use XAML 2009 features together with `x:TypeArguments` but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="17fe0-141">XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento las palabras clave y características de XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="17fe0-141">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span> <span data-ttu-id="17fe0-142">Si se necesita compilación de marcado XAML, debe funcionar en las restricciones que se indican en la sección "XAML 2006 y WPF genérica usos XAML".</span><span class="sxs-lookup"><span data-stu-id="17fe0-142">If you need to markup compile the XAML, you must operate under the restrictions noted in the "XAML 2006 and WPF Generic XAML Usages" section.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17fe0-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="17fe0-143">See Also</span></span>  
 [<span data-ttu-id="17fe0-144">x:Class (Directiva)</span><span class="sxs-lookup"><span data-stu-id="17fe0-144">x:Class Directive</span></span>](../../../docs/framework/xaml-services/x-class-directive.md)  
 [<span data-ttu-id="17fe0-145">x:Type (extensión de marcado)</span><span class="sxs-lookup"><span data-stu-id="17fe0-145">x:Type Markup Extension</span></span>](../../../docs/framework/xaml-services/x-type-markup-extension.md)  
 [<span data-ttu-id="17fe0-146">Tipos integrados para primitivas comunes en el lenguaje XAML</span><span class="sxs-lookup"><span data-stu-id="17fe0-146">Built-in Types for Common XAML Language Primitives</span></span>](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)  
 [<span data-ttu-id="17fe0-147">Elementos genéricos en XAML</span><span class="sxs-lookup"><span data-stu-id="17fe0-147">Generics in XAML</span></span>](../../../docs/framework/xaml-services/generics-in-xaml.md)
