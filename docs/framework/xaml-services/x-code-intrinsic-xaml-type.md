---
title: "x:Code Intrinsic XAML Type | Microsoft Docs"
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
  - "Code"
  - "x:Code"
  - "xCode"
helpviewer_keywords: 
  - "Code directive in XAML [XAML Services]"
  - "x:Code XAML directive element [XAML Services]"
  - "XAML [XAML Services], x:Code directive element"
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
caps.latest.revision: 19
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 19
---
# x:Code Intrinsic XAML Type
Permite la posición de código dentro de una producción XAML.  Cualquier implementación de procesador XAML que compile XAML puede compilar este código, o dejarlo en la producción de XAML para usos posteriores como interpretación por un runtime.  
  
## Uso de elementos de objeto XAML  
  
```  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## Comentarios  
 El código incluido en el elemento de directiva `x:Code` de XAML se interpreta en el espacio de nombres XML general y de los espacios de nombres proporcionados.  Por consiguiente, suele ser necesario incluir también el código utilizado por `x:Code` dentro de un segmento `CDATA`.  
  
 `x:Code` no se permite para todos los mecanismos de implementación posibles de una producción XAML.  En marcos concretos \(por ejemplo WPF\) el código debe estar compilado.  En otros marcos, la utilización `x:Code` no podría permitirse generalmente.  
  
 En marcos de trabajo que permiten contenido `x:Code` administrado, los valores y destinos del proyecto contenedor que se utiliza para compilar la aplicación determinan el compilador del lenguaje correcto que se debe utilizar para el contenido de `x:Code`.  
  
## Notas de uso de WPF  
 El código declarado dentro de `x:Code` para WPF tiene varias limitaciones notables:  
  
-   El elemento de directiva `x:Code` debe ser un elemento secundario inmediato del elemento raíz de la producción XAML.  
  
-   [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md) se debe proporcionar en el elemento raíz primario.  
  
-   La compilación tratará el código colocado dentro de `x:Code` como si estuviera dentro del ámbito de la clase parcial que ya se está creando para esa página XAML.  Por consiguiente, todo el código que se defina deberá estar constituido por miembros o variables de esa clase parcial.  
  
-   No se pueden definir clases adicionales, excepto mediante anidación de una clase dentro de la clase parcial \(se permite el anidamiento, pero no es habitual porque en XAML no se puede hacer referencia a las clases anidadas\).  No se pueden definir ni agregar otros espacios de nombres CLR distintos al espacio de nombres utilizado para la clase parcial existente.  
  
-   Las referencias a entidades de código que se encuentren fuera del espacio de nombres CLR de la clase parcial deben ser siempre completas.  Si los miembros que se declaran son invalidaciones de miembros invalidables de la clase parcial, esto se debe especificar mediante la palabra clave de invalidación específica del lenguaje.  Si miembros declarados en `x:Code` están en conflicto con miembros de la clase parcial creados fuera de XAML, de tal forma que el compilador notifica el conflicto, el archivo XAML no se puede cargar ni compilar.  
  
## Vea también  
 [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md)   
 [Código subyacente y XAML en WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)   
 [Información general sobre XAML \(WPF\)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)