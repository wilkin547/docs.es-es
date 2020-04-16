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
ms.openlocfilehash: 4da72ed630c1df001e3fd6c7e55f866b94c4d9b1
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432807"
---
# <a name="xcode-intrinsic-xaml-type"></a>x:Code (Tipo XAML intrínseco)
Permite la colocación de código dentro de una producción XAML. Dicho código se puede compilar mediante cualquier implementación de procesador XAML que compile XAML o dejaren en la producción XAML para usos posteriores, como la interpretación por un tiempo de ejecución.

## <a name="xaml-object-element-usage"></a>Uso de elementos de objeto XAML

```xaml
<x:Code>
   // code instructions, usually enclosed by CDATA...
</x:Code>
```

## <a name="remarks"></a>Observaciones

El código `x:Code` dentro del elemento de directiva XAML todavía se interpreta dentro del espacio de nombres XML general y los espacios de nombres XAML proporcionados. Por lo tanto, normalmente es necesario `x:Code` incluir `CDATA` el código utilizado para dentro de un segmento.

`x:Code`no está permitido para todos los mecanismos de implementación posibles de una producción XAML. En marcos específicos (por ejemplo, WPF) el código debe compilarse. En otros marcos, `x:Code` el uso podría no permitirse en general.

Para los marcos `x:Code` que permiten el contenido administrado, el compilador de lenguaje correcto que se usará para `x:Code` el contenido viene determinado por la configuración y los destinos del proyecto contenedor que se usa para compilar la aplicación.

## <a name="wpf-usage-notes"></a>Notas de uso de WPF

El código `x:Code` declarado dentro de WPFWPF tiene varias limitaciones notables:

- El `x:Code` elemento de directiva debe ser un elemento secundario inmediato del elemento raíz de la producción XAML.

- [x:La Directiva de clase](xclass-directive.md) debe proporcionarse en el elemento raíz primario.

- El código `x:Code` colocado dentro se tratará mediante compilación para que esté dentro del ámbito de la clase parcial que ya se está creando para esa página XAML. Por lo tanto, todo el código que defina debe ser miembros o variables de esa clase parcial.

- No se pueden definir clases adicionales, excepto anidando una clase dentro de la clase parcial (se permite el anidamiento, pero no es típico porque no se puede hacer referencia a las clases anidadas en XAML). Los espacios de nombres CLR distintos del espacio de nombres que se usa para la clase parcial existente no se pueden definir ni agregar.

- Las referencias a entidades de código fuera del espacio de nombres CLR de clase parcial deben estar completamente calificadas. Si los miembros que se declaran son invalidaciones de los miembros reemplazables de clase parcial, debe especificarse con la palabra clave override específica del idioma. Si los `x:Code` miembros declarados en el ámbito entran en conflicto con los miembros de la clase parcial creada a partir del XAML, de forma que el compilador notifica el conflicto, el archivo XAML no puede compilar ni cargar.

## <a name="see-also"></a>Consulte también

- [x:Class (Directiva)](xclass-directive.md)
- [Código subyacente y XAML en WPF](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Información general sobre XAML (WPF)](../fundamentals/xaml.md)
