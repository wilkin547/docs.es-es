---
title: x:Code (Tipo XAML intrínseco)
ms.date: 03/30/2017
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
ms.openlocfilehash: 7bb78b05be7b3edc4471bc276010eabd92a07a14
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145241"
---
# <a name="xcode-intrinsic-xaml-type"></a>x:Code (Tipo XAML intrínseco)
Permite la selección de ubicación de código dentro de una producción de XAML. Dicho código puede compilarse por cualquier implementación de procesador XAML que se compila en XAML o a la izquierda en la producción de XAML para usos posteriores como interpretación por un tiempo de ejecución.  
  
## <a name="xaml-object-element-usage"></a>Uso de elementos de objeto XAML  
  
```  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a>Comentarios  
 El código dentro de la `x:Code` elemento de directiva de XAML es todavía interpretado dentro del espacio de nombres XML general y los espacios de nombres XAML proporcionados. Por lo tanto, resulta suele ser necesario incluir el código utilizado para `x:Code` dentro de un `CDATA` segmento.  
  
 `x:Code` no se permite para todos los mecanismos de implementación posibles de una producción de XAML. El código debe compilarse en marcos concretos (por ejemplo, WPF). En otros marcos, `x:Code` podría denegar uso general.  
  
 Para los marcos que permiten administrado `x:Code` de contenido, el compilador del lenguaje correcto que se usará para `x:Code` contenido viene determinado por la configuración y los destinos del proyecto contenedor que se utiliza para compilar la aplicación.  
  
## <a name="wpf-usage-notes"></a>Notas de uso WPF  
 Código declarados dentro de `x:Code` para WPF tiene varias limitaciones importantes:  
  
-   El `x:Code` elemento de directiva debe ser un elemento secundario inmediato del elemento raíz de la producción de XAML.  
  
-   [x: Class directiva](x-class-directive.md) debe proporcionarse en el elemento raíz primario.  
  
-   El código se coloca dentro de `x:Code` se tratará de compilación dentro del ámbito de la clase parcial que ya se está creando para esa página XAML. Por lo tanto, todo el código que defina debe ser miembros o las variables de la clase parcial.  
  
-   No se puede definir clases adicionales, aparte de mediante el anidamiento de una clase dentro de la clase parcial (se permite el anidamiento, pero no es habitual, ya que no se puede hacer referencia a clases anidadas en XAML). No se define o agregado a espacios de nombres CLR que no sea el espacio de nombres que se usa para la clase parcial existente.  
  
-   Las referencias a entidades de código fuera del espacio de nombres CLR de la clase parcial deben ubicarse completas. Si los miembros que se declara reemplazos para los miembros de clase parcial que se puede invalidar, esto debe especificarse con la palabra clave override específicos del idioma. Si los miembros declaran en `x:Code` ámbito entran en conflicto con los miembros de la clase parcial creada desde el XAML, de tal forma que el compilador informa el conflicto, el archivo XAML no se puede compilar o cargar.  
  
## <a name="see-also"></a>Vea también

- [x:Class (Directiva)](x-class-directive.md)
- [Código subyacente y XAML en WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Información general sobre XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md)
