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
ms.openlocfilehash: 2b7713548b6269f079ef32b5bf1fe4fa630edcc8
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053793"
---
# <a name="xcode-intrinsic-xaml-type"></a>x:Code (Tipo XAML intrínseco)
Permite colocar código dentro de un entorno de producción XAML. Este código se puede compilar con cualquier implementación de procesador XAML que compile XAML, o bien en la producción XAML para usos posteriores, como la interpretación de un Runtime.  
  
## <a name="xaml-object-element-usage"></a>Uso de elementos de objeto XAML  
  
```xaml  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a>Comentarios  
 El código dentro del `x:Code` elemento de directiva de XAML se interpreta en el espacio de nombres XML general y en los espacios de nombres XAML proporcionados. Por lo tanto, normalmente es necesario incluir el código utilizado para `x:Code` dentro de `CDATA` un segmento.  
  
 `x:Code`no está permitida para todos los mecanismos de implementación posibles de una producción de XAML. En marcos de trabajo específicos (por ejemplo, WPF), se debe compilar el código. En otros marcos, `x:Code` el uso podría no estar permitido por lo general.  
  
 En el caso de los marcos `x:Code` que permiten contenido administrado, el compilador `x:Code` de lenguaje correcto que se va a usar para el contenido está determinado por la configuración y los destinos del proyecto contenedor que se usa para compilar la aplicación.  
  
## <a name="wpf-usage-notes"></a>Notas de uso de WPF  
 El código declarado `x:Code` en para WPF tiene varias limitaciones importantes:  
  
- El `x:Code` elemento de Directiva debe ser un elemento secundario inmediato del elemento raíz de la producción XAML.  
  
- se debe proporcionar la [Directiva x:Class](x-class-directive.md) en el elemento raíz primario.  
  
- El código colocado dentro `x:Code` de se tratará mediante compilación para que esté dentro del ámbito de la clase parcial que ya se está creando para esa página XAML. Por lo tanto, todo el código que defina debe ser miembro o variables de esa clase parcial.  
  
- No se pueden definir clases adicionales, aparte de anidar una clase dentro de la clase parcial (se permite el anidamiento, pero no es típico porque no se puede hacer referencia a las clases anidadas en XAML). Los espacios de nombres CLR distintos del espacio de nombres que se usa para la clase parcial existente no se pueden definir ni agregar a.  
  
- Todas las referencias a entidades de código fuera del espacio de nombres CLR de clase parcial deben ser completas. Si los miembros que se declaran son invalidaciones de los miembros reemplazables de clase parcial, debe especificarse con la palabra clave override específica del lenguaje. Si los miembros declarados en el ámbito entran en `x:Code` conflicto con los miembros de la clase parcial creada fuera del código XAML, de tal forma que el compilador notifique el conflicto, el archivo XAML no se puede compilar ni cargar.  
  
## <a name="see-also"></a>Vea también

- [x:Class (Directiva)](x-class-directive.md)
- [Código subyacente y XAML en WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Información general sobre XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md)
