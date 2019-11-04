---
title: Control de xml:space en XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 8f860f5ee42b5c1df43c4ec2b1003408bc1c0d8e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458794"
---
# <a name="xmlspace-handling-in-xaml"></a>Control de xml:space en XAML
El atributo `xml:space` es un atributo definido por XML que declara el comportamiento de procesamiento de espacios en blanco significativo dentro de un elemento de objeto. Este comportamiento es relevante para todo el contenido (texto interno) incluido en el elemento en el que se declara `xml:space`, y también se limita a los elementos secundarios.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 \- o -  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a>Comentarios  
 La definición del atributo `xml:space` en XAML, incluidos sus dos valores posibles, se deriva de `xml:space` como se define como un "atributo especial" por las especificaciones del W3C para XML.  
  
 El valor predeterminado del atributo `xml:space` es el valor literal `"default"`. En el caso del valor `"default"`, o si `xml:space` no se indica en absoluto, el comportamiento del análisis de espacio en blanco significativo es el control predeterminado, tal y como se define en el tema [procesamiento de espacios en blanco en XAML](whitespace-processing-in-xaml.md).  
  
 Para conservar el espacio en blanco dentro del contenido del elemento de objeto, especifique `xml:space="preserve"` en ese elemento de objeto.  
  
 En la mayoría de las interpretaciones, los efectos del atributo `xml:space` y el valor del atributo se limitan a los elementos secundarios.  
  
 Para obtener información completa sobre el procesamiento de espacios en blanco en XAML, vea [procesamiento de espacios en blanco en XAML](whitespace-processing-in-xaml.md).  
  
## <a name="see-also"></a>Vea también

- [Procesamiento de espacios en blanco en XAML](whitespace-processing-in-xaml.md)
- [Información general sobre XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)
