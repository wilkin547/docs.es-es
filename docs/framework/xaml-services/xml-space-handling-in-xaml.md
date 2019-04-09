---
title: Control de xml:space en XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: d15bab1ad9234959048fa7b7c3fa2bbbeca5fe6e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193322"
---
# <a name="xmlspace-handling-in-xaml"></a>Control de xml:space en XAML
El `xml:space` es un atributo definido por el XML que declara el comportamiento de procesamiento de espacios en blanco significativos dentro de un elemento de objeto. Este comportamiento es relevante para todo el contenido (texto interno) incluido dentro del elemento donde `xml:space` se declara y también limita su ámbito a los elementos secundarios.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 \- o -  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a>Comentarios  
 La definición de la `xml:space` se deriva de atributo en XAML, incluidos sus dos valores posibles `xml:space` tal como se define como un "atributo especial" por las especificaciones de W3C para XML.  
  
 El valor predeterminado de la `xml:space` atributo es el valor literal `"default"`. Para el valor `"default"`, o si `xml:space` no se indica en absoluto, el comportamiento de análisis de espacio en blanco significativo es el control predeterminado, tal como se define en el tema [espacio en blanco en XAML de procesamiento](whitespace-processing-in-xaml.md).  
  
 Para conservar espacio en blanco dentro del contenido del elemento de objeto, especifique `xml:space="preserve"` en ese elemento de objeto.  
  
 En la mayoría de las interpretaciones el `xml:space` efectos del atributo y el valor del atributo se limitan a los elementos secundarios.  
  
 Para obtener una explicación completa de espacio en blanco en XAML de procesamiento, vea [espacio en blanco en XAML de procesamiento](whitespace-processing-in-xaml.md).  
  
## <a name="see-also"></a>Vea también

- [Procesamiento de espacios en blanco en XAML](whitespace-processing-in-xaml.md)
- [Información general sobre XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md)
