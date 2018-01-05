---
title: "x:Code (Tipo XAML intrínseco)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
caps.latest.revision: "19"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d39249a5d1c0e230d21e6d889b92d0b57c98e2ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="xcode-intrinsic-xaml-type"></a>x:Code (Tipo XAML intrínseco)
Permite la colocación de código dentro de una producción de XAML. O bien se puede compilar este código si cualquier implementación de procesador XAML que compila XAML o a la izquierda en la producción de XAML para usos posteriores como interpretación por un runtime.  
  
## <a name="xaml-object-element-usage"></a>Uso de elementos de objeto XAML  
  
```  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a>Comentarios  
 El código dentro de la `x:Code` elemento de directiva de XAML es sigue interpretado dentro del espacio de nombres XML general y los espacios de nombres XAML proporcionado. Por lo tanto, resulta suele ser necesario incluir el código utilizado para `x:Code` dentro de un `CDATA` segmento.  
  
 `x:Code`no se permite para todos los mecanismos de implementación posibles de una producción de XAML. En marcos concretos (por ejemplo, WPF) se debe compilar el código. En otros marcos, `x:Code` uso no podría permitirse generalmente.  
  
 Para los marcos de trabajo que permiten administrado `x:Code` de contenido, el compilador del lenguaje correcto que se usará para `x:Code` contenido viene determinado por la configuración y los destinos del proyecto contenedor que se utiliza para compilar la aplicación.  
  
## <a name="wpf-usage-notes"></a>Notas de uso WPF  
 Código declarados dentro de `x:Code` para WPF tiene varias limitaciones importantes:  
  
-   El `x:Code` elemento de directiva debe ser un elemento secundario inmediato del elemento raíz de la producción de XAML.  
  
-   [x: Class Directive](../../../docs/framework/xaml-services/x-class-directive.md) debe proporcionarse en el elemento raíz primario.  
  
-   El código se coloca dentro de `x:Code` tratará la compilación para estar dentro del ámbito de la clase parcial que ya se está creando para esa página XAML. Por lo tanto, todo el código que defina debe ser miembros o variables de esa clase parcial.  
  
-   No se puede definir clases adicionales, no sea anidando una clase dentro de la clase parcial (está permitido el anidamiento, pero no es normal, porque no se pueden hacer referencia a las clases anidadas en XAML). Espacios de nombres CLR que no sea el espacio de nombres que se usa para la clase parcial existente se no se define o agregar a.  
  
-   Las referencias a entidades de código fuera del espacio de nombres CLR de clase parcial deben ser completas. Si los miembros que se declara son invalidaciones para los miembros reemplazables de clase parcial, éste debe especificarse con la palabra clave override específicos del idioma. Si los miembros declarados en `x:Code` ámbito entran en conflicto con los miembros de la clase parcial creados fuera de XAML, de tal manera que el compilador informa de los conflictos, el archivo XAML no se cargará ni compilará.  
  
## <a name="see-also"></a>Vea también  
 [x:Class (Directiva)](../../../docs/framework/xaml-services/x-class-directive.md)  
 [Código subyacente y XAML en WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [Información general sobre XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
