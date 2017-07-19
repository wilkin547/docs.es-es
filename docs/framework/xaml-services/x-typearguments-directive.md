---
title: "x:TypeArguments Directive | Microsoft Docs"
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
  - "x:TypeArguments"
  - "xTypeArguments"
  - "TypeArguments"
helpviewer_keywords: 
  - "x:TypeArguments attribute [XAML Services]"
  - "TypeArguments attribute in XAML [XAML Services]"
  - "XAML [XAML Services], x:TypeArguments attribute"
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
caps.latest.revision: 18
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 18
---
# x:TypeArguments Directive
Pasa argumentos de tipo restrictivos de un genérico al constructor del tipo genérico.  
  
## Uso de atributos XAML  
  
```  
<object x:TypeArguments="typeString" .../>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|`object`|Una declaración del elemento de objeto de un tipo XAML, que está respaldado por un tipo genérico de CLR.  Si `object` hace referencia a un tipo XAML que no es del espacio de nombres XAML predeterminado, `object` requiere un prefijo para indicar el espacio de nombres XAML donde existe `object`.|  
|`typeString`|Cadena que declara uno o más nombres de tipo XAML como cadenas, que proporciona los argumentos de tipo para el tipo genérico de CLR.  Vea Comentarios para obtener notas de sintaxis adicionales.|  
  
## Comentarios  
 En la mayoría de los casos, los tipos XAML que se utilizan como elemento de información en una cadena `typeString` llevan prefijo.  Los tipos típicos de restricciones genéricas de \(por ejemplo, <xref:System.Int32> y <xref:System.String>\) de CLR proceden de bibliotecas de clases base de CLR.  Esas bibliotecas no están asignadas a los típicos espacios de nombres XAML predeterminados específicos de marco y, en consecuencia, requieren una asignación de prefijo para el uso de XAML.  
  
 Es posible especificar más de un nombre de tipo XAML mediante un delimitador de coma.  
  
 Si las propias restricciones genéricas usan tipos genéricos, los argumentos de tipo de restricción anidados pueden estar entre paréntesis \(\).  
  
 Observe que esta definición de `x:TypeArguments` es específica de los servicios XAML de .NET Framework y utiliza el respaldo de CLR.  Una definición de nivel del lenguaje se puede encontrar en [\[MS\-XAML\] sección 5.3.11](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
## Ejemplo de uso  
 Para obtener estos ejemplos, suponga que se declaran las siguientes definiciones de espacio de nombres XAML:  
  
```  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### List\<String\>  
 `<scg:List x:TypeArguments="sys:String" ...>` crea instancias de un nuevo <xref:System.Collections.Generic.List%601> con un argumento de tipo <xref:System.String>.  
  
### Dictionary\<String,String\>  
 `<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` crea instancias de un nuevo <xref:System.Collections.Generic.Dictionary%602> con dos argumentos de tipo <xref:System.String>.  
  
### Queue\<KeyValuePair\<String,String\>\>  
 `<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` crea instancias de un nuevo objeto <xref:System.Collections.Generic.Queue%601> que tiene una restricción de <xref:System.Collections.Generic.KeyValuePair%602>, con los argumentos de tipo de restricción interna <xref:System.String> y <xref:System.String>.  
  
## XAML 2006 y usos de XAML genéricos de WPF  
 Para la utilización de XAML 2006 y el XAML que se usa en las aplicaciones WPF, las siguientes restricciones existen para `x:TypeArguments` y los usos de tipo genérico de XAML en general:  
  
-   Sólo el elemento raíz de un archivo XAML puede admitir una utilización de XAML genérica que hace referencia a un tipo genérico.  
  
-   El elemento raíz debe asignarse a un tipo genérico con, al menos, un argumento de tipo.  Un ejemplo de ello sería <xref:System.Windows.Navigation.PageFunction%601>.  Las funciones de página son el escenario primario para la compatibilidad del uso genérico de XAML en WPF.  
  
-   El elemento de objeto XAML de elemento raíz para el genérico también debe declarar una clase parcial, mediante `x:Class`.  Esto es true aun cuando se define una acción de compilación de WPF.  
  
-   `x:TypeArguments` no puede hacer referencia a las restricciones genéricas anidadas.  
  
## XAML 2009 o XAML 2006 sin dependencia de WPF 3.0 o WPF 3.5  
 En los servicios XAML de .NET Framework para XAML 2006 o XAML 2009, las restricciones relativas a WPF en el uso de XAML genérico son flexibles.  Puede crear instancias de un elemento de objeto genérico en cualquier posición del marcado XAML que puede admitir el sistema de tipos de respaldo y el modelo de objetos.  
  
 Si usa XAML 2009, en lugar de asignar los tipos base de CLR para obtener tipos XAML para los primitivos del lenguaje comunes, puede usar los [Tipos integrados para primitivas comunes en el lenguaje XAML](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) como elementos de información en `typeString`.  Por ejemplo, podría declarar lo siguiente \(las asignaciones de prefijo no se muestran, pero x es el espacio de nombres XAML del lenguaje XAML para XAML 2009\):  
  
```  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 En WPF y cuando el destino es [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], puede usar las características de XAML 2009 junto con `x:TypeArguments`, pero solo para XAML separado \(no compilado por marcado\).  El XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten actualmente las palabras clave y características de XAML 2009.  Si se necesita una compilación de marcado de XAML, se debe operar según las restricciones citadas en la sección "XAML 2006 y usos de XAML genéricos de WPF".  
  
## Vea también  
 [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md)   
 [x:Type Markup Extension](../../../docs/framework/xaml-services/x-type-markup-extension.md)   
 [Tipos integrados para primitivas comunes en el lenguaje XAML](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)   
 [Generics in XAML](../../../docs/framework/xaml-services/generics-in-xaml.md)