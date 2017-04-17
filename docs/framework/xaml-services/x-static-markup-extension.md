---
title: "x:Static Markup Extension | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "StaticExtension"
  - "xStatic"
  - "x:Static"
helpviewer_keywords: 
  - "x:Static markup extension [XAML Services]"
  - "Static markup extension in XAML [XAML Services]"
  - "XAML [XAML Services], x:Static markup extension"
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
caps.latest.revision: 25
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 25
---
# x:Static Markup Extension
Hace referencia a cualquier entidad de código estática por valor definida conforme a [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)].  La propiedad estática a la que se hace referencia se puede usar para proporcionar el valor de una propiedad en XAML.  
  
## Uso de atributos XAML  
  
```  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|`prefix`|Opcional.  Prefijo que se refiere a un espacio de nombres XAML asignado, no predeterminado.  `prefix` se muestra explícitamente en la utilización porque raramente se hace referencia a las propiedades estáticas que proceden de un espacio de nombres XAML predeterminado.  Vea la sección Comentarios.|  
|`typeName`|Obligatorio.  Nombre del tipo que define el miembro estático deseado.|  
|`staticMemberName`|Obligatorio.  Nombre del miembro de valor estático deseado \(una constante, una propiedad estática, un campo o un valor de enumeración\).|  
  
## Comentarios  
 La entidad de código a la que se hace referencia debe ser una de las siguientes:  
  
-   Constante.  
  
-   Una propiedad estática  
  
-   Un campo  
  
-   Valor de enumeración  
  
 Especificar cualquier otra entidad del código, como una propiedad no estática, provoca un error del tiempo de compilación si el XAML es marcado compilado o una excepción de análisis en tiempo de carga de XAML.  
  
 Se puede hacer referencias `x:Static` a campos estáticos o propiedades que no pertenezcan al espacio de nombres XAML predeterminado en el documento XAML; no obstante, para ello se requiere una asignación de prefijo.  Los espacios de nombres XAML se definen casi siempre en el elemento raíz del documento XAML.  
  
 Los servicios XAML de .NET Framework, así como sus lectores XAML y sistemas de escritura XAML pueden realizar operaciones de búsqueda para las propiedades estáticas, al ejecutarse con el contexto de esquema XAML predeterminado.  Este contexto de esquema XAML puede utilizar la reflexión de CLR para proporcionar los valores estáticos necesarios para la construcción del gráfico de objeto.  El `typeName` que se especifica es realmente un nombre de tipo XAML, no un nombre de tipo de CLR, si bien estos son básicamente el mismo nombre cuando se usa el contexto de esquema XAML predeterminado o se utilizan todos los marcos de implementación de XAML basados en CLR existentes.  
  
 Extreme las precauciones cuando haga referencias a `x:Static` que no son directamente el tipo de valor de una propiedad.  En la secuencia del procesamiento XAML, los valores proporcionado de una extensión de marcado no invocan conversión de valor adicional.  Esto es true incluso si la referencia `x:Static` crea una cadena de texto, y suele producirse una conversión de valor para los valores de atributo basados en cadena de texto para ese miembro concreto o para cualquier valor de miembro del tipo devuelto.  
  
 La sintaxis de atributo es la que se usa más a menudo con esta extensión de marcado.  El token de cadena que se proporciona después de la cadena de identificador `x:Static` se asigna como valor de <xref:System.Windows.Markup.StaticExtension.Member%2A> de la clase de extensión <xref:System.Windows.Markup.StaticExtension> subyacente.  
  
 Existen otros dos usos de XAML que son técnicamente posibles.  Sin embargo, estos usos son menos comunes porque están detallados innecesariamente:  
  
 **Sintaxis de elementos de objeto:** `<x:Static Member="``prefix``:``typeName``.``staticMemberName``" .../>`  
  
 **Sintaxis de atributo con propiedad Member explícita para la cadena de inicialización:** `<` `object` `` `property` `="{x:Static Member=` `prefix` `:` `typeName` `.` `staticMemberName` `}" .../>`  
  
 La clase <xref:System.Windows.Markup.StaticExtension> define el control para esta extensión de marcado en la implementación de servicios XAML de .NET Framework.  
  
 `x:Static` es una extensión de marcado.  Todas las extensiones de marcado de código XAML usan caracteres `{` y `}` en su sintaxis de atributo, que es la convención que permite que un procesador XAML reconozca que una extensión de marcado debe proporcionar un valor.  Para obtener más información sobre las extensiones de marcado, vea [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).  
  
## Notas de uso de WPF  
 El espacio de nombres XAML predeterminado que utiliza para programación de WPF no contiene muchas propiedades estáticas útiles, y la mayoría de las propiedades estáticas útiles tienen apoyo tales como los convertidores de tipos que facilitan la utilización sin requerir `{x:Static}`.  Para las propiedades estáticas, debe asignar un prefijo para un espacio de nombres XAML si se cumple una de las condiciones siguientes:  
  
-   Se hace referencia a un tipo que existe en WPF pero que no forma parte del espacio de nombres XAML predeterminado de WPF \([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]\).  Éste es un escenario relativamente común para utilizar `x:Static`.  Por ejemplo, puede usar una referencia `x:Static` con un espacio de nombres XAML que se asigna al espacio de nombres <xref:System> de CLR y al ensamblado mscorlib a fin de hacer referencia a las propiedades estáticas de la clase <xref:System.Environment>.  
  
-   Se hace referencia a un tipo de un ensamblado personalizado.  
  
-   Se hace referencia a un tipo que existe en un ensamblado de WPF, pero ese tipo se encuentra dentro de un espacio de nombres CLR que no se ha asignado de manera que forme parte del espacio de nombres XAML predeterminado de WPF.  Las definiciones en varios ensamblados de WPF \(para obtener más información sobre este concepto, vea [Espacios de nombres y asignación de espacios de nombres XAML para WPF](../../../ocs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)\), realizan la asignación de espacios de nombres CLR en el espacio de nombres XAML predeterminado para WPF.  Los espacios de nombres CLR sin asignar pueden existir si el espacio de nombres CLR se compone mayoritariamente de las definiciones de clase que no suelen estar pensados para XAML, como <xref:System.Windows.Threading>.  
  
 Para obtener más información sobre cómo usar prefijos y espacios de nombres XAML en WPF, vea [Espacios de nombres y asignación de espacios de nombres XAML para WPF](../../../ocs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
## Vea también  
 [x:Type Markup Extension](../../../docs/framework/xaml-services/x-type-markup-extension.md)   
 [Types Migrated from WPF to System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)