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
# <a name="xtypearguments-directive"></a>x:TypeArguments (Directiva)
Pasa al restringir los argumentos de un tipo genérico para el constructor del tipo genérico de tipo.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object x:TypeArguments="typeString" .../>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`object`|Una declaración de elemento de objeto de un tipo XAML, que está respaldado por un tipo genérico de CLR. Si `object` hace referencia a un tipo XAML que no esté en el espacio de nombres XAML predeterminado, `object` requiere un prefijo para indicar el espacio de nombres XAML donde `object` existe.|  
|`typeString`|Una cadena que declara uno o más XAML escriba nombres como cadenas, lo que proporciona los argumentos de tipo para el tipo genérico de CLR. Vea la sección Comentarios para obtener notas adicionales de la sintaxis.|  
  
## <a name="remarks"></a>Comentarios  
 En la mayoría de los casos, los tipos XAML que se usan como un elemento de información en un `typeString` cadena tienen el prefijo. Los tipos típicos de restricciones genéricas de CLR (por ejemplo, <xref:System.Int32> y <xref:System.String>) proceden de bibliotecas de clases base de CLR. Esas bibliotecas no están asignadas a típica predeterminada específica del marco espacios de nombres XAML y, por lo tanto, requieren una asignación de prefijo para el uso XAML.  
  
 Puede especificar más de un nombre de tipo XAML mediante un delimitador de coma.  
  
 Si las propias restricciones genéricas usan tipos genéricos, los argumentos de tipo de restricción anidados pueden estar contenidos en paréntesis ().  
  
 Tenga en cuenta que esta definición de `x:TypeArguments` es específica a los servicios XAML de .NET Framework y utilizar copias de seguridad de CLR. Una definición de nivel de lenguaje se puede encontrar en [ \[MS-XAML\] sección 5.3.11](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="usage-examples"></a>Ejemplos de uso  
 Para estos ejemplos, se supone que se declaran las siguientes definiciones de espacio de nombres XAML:  
  
```  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a>Lista\<cadena >  
 `<scg:List x:TypeArguments="sys:String" ...>`crea una instancia de un nuevo <xref:System.Collections.Generic.List%601> con una <xref:System.String> el argumento de tipo.  
  
### <a name="dictionarystringstring"></a>Diccionario\<cadena, cadena >  
 `<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>`crea una instancia de un nuevo <xref:System.Collections.Generic.Dictionary%602> con dos <xref:System.String> argumentos de tipo.  
  
### <a name="queuekeyvaluepairstringstring"></a>Cola < KeyValuePair\<cadena, cadena >>  
 `<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>`crea una instancia de un nuevo <xref:System.Collections.Generic.Queue%601> que tiene una restricción de <xref:System.Collections.Generic.KeyValuePair%602> con los argumentos de tipo de restricción interna <xref:System.String> y <xref:System.String>.  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a>Usos XAML genéricos de XAML 2006 y WPF  
 Para el uso de XAML 2006 y XAML que se usa para las aplicaciones WPF, existen las siguientes restricciones para `x:TypeArguments` y usos de tipo genérico de XAML en general:  
  
-   Solo el elemento raíz de un archivo XAML puede admitir un uso XAML genérico que hace referencia a un tipo genérico.  
  
-   El elemento raíz debe asignar a un tipo genérico con al menos un argumento de tipo. Un ejemplo es <xref:System.Windows.Navigation.PageFunction%601>. Las funciones de página son el escenario principal para la compatibilidad de uso genérico de XAML en WPF.  
  
-   El elemento de objeto XAML de elemento raíz para el genérico también debe declarar una clase parcial con `x:Class`. Esto es cierto incluso si la acción de compilación de definir un WPF.  
  
-   `x:TypeArguments`no se puede hacer referencia a las restricciones genéricas anidadas.  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a>XAML 2009 o XAML 2006 con ningún WPF 3.0 o 3.5 de WPF dependencia  
 En servicios de XAML de .NET Framework para XAML 2006 o XAML 2009, se relajan las restricciones relacionadas con WPF en el uso XAML genérico. Puede crear una instancia de un elemento de objeto genérico en cualquier posición del marcado XAML que puede admitir el modelo de objeto y de sistema de tipos de respaldo.  
  
 Si utiliza XAML 2009 en lugar de asignar el CLR de tipos para obtener tipos XAML para los primitivos del lenguaje común base, puede usar [tipos integrados para primitivas del lenguaje XAML común](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) como elementos de información en un `typeString`. Por ejemplo, podría declarar lo siguiente (asignaciones de prefijos no se muestran, pero x es el espacio de nombres XAML del lenguaje XAML para XAML 2009):  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 En WPF y cuando el destino es [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], puede usar las características de XAML 2009 junto con `x:TypeArguments` , pero solo para XAML dinámico (XAML que no está compilado por marcado). XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento las palabras clave y características de XAML 2009. Si se necesita compilación de marcado XAML, debe funcionar en las restricciones que se indican en la sección "XAML 2006 y WPF genérica usos XAML".  
  
## <a name="see-also"></a>Vea también  
 [x:Class (Directiva)](../../../docs/framework/xaml-services/x-class-directive.md)  
 [x:Type (extensión de marcado)](../../../docs/framework/xaml-services/x-type-markup-extension.md)  
 [Tipos integrados para primitivas comunes en el lenguaje XAML](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)  
 [Elementos genéricos en XAML](../../../docs/framework/xaml-services/generics-in-xaml.md)
