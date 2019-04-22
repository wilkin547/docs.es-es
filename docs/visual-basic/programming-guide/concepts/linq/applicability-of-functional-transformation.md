---
title: Aplicabilidad de la transformación funcional (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 3b74e134-e19b-44bc-8d06-e26c48305040
ms.openlocfilehash: 7efeab82dafc284f64a950eb7f5e4a6ee3f2e73d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827619"
---
# <a name="applicability-of-functional-transformation-visual-basic"></a>Aplicabilidad de la transformación funcional (Visual Basic)
Las transformaciones funcionales puras se pueden aplicar en una amplia variedad de situaciones.  
  
 El enfoque de transformación funcional es especialmente adecuado para consultar y manipular datos estructurados; por lo tanto encaja bien con las tecnologías LINQ. No obstante, la transformación funcional tiene una aplicabilidad mucho más amplia que el uso con LINQ. Cualquier proceso en el que el centro de atención principal sea la transformación de datos de un formato a otro probablemente debe considerarse un candidato para la transformación funcional.  
  
 Este enfoque es aplicable a muchos problemas que a primera vista pueden no parecer candidatos. La transformación funcional, usada en conjunción con o de forma separada de LINQ, debe tenerse en cuenta para las siguientes áreas:  
  
-   Documentos basados en XML. Los datos bien formados de cualquier dialecto XML se pueden manipular fácilmente mediante la transformación funcional. Para obtener más información, consulte [transformación funcional en XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-transformation-of-xml.md).  
  
-   Otros formatos de archivo estructurados. Desde archivos Windows.ini a documentos de texto sin formato, la mayoría de archivos tienen alguna estructura que se presta a análisis y transformación.  
  
-   Protocolos de secuencia de datos. La codificación y decodificación de datos de protocolos de comunicación a menudo se puede representar con una sencilla transformación funcional.  
  
-   Datos RDBMS y OODBMS. Las bases de datos relacionales y orientadas a objetos, como XML, son orígenes de datos estructurados muy utilizados.  
  
-   Soluciones científicas, estadísticas y matemáticas. Estos campos suelen manipular grandes cantidades de datos para ayudar al usuario a visualizar, estimar o resolver problemas que no son triviales.  
  
 Como se describe en [refactorizar en funciones puras (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md), usando funciones puras es un ejemplo de la programación funcional. Además de sus ventajas inmediatas, el uso de funciones puras proporciona una valiosa experiencia para la resolución de problemas desde una perspectiva de transformación funcional. Este enfoque también puede tener un gran impacto en el diseño de clases y la programación. Éste es el caso cuando un problema se presta a una solución de transformación de datos tal como se ha escrito anteriormente.  
  
 Aunque quedan fuera del ámbito de este tutorial, los diseños que tienen la influencia de la perspectiva de transformación funcional tienden a centrarse en procesos más que en objetos como actores y la solución resultante tiende a implementarse como una serie de transformaciones a gran escala en lugar de cambios de estado de objeto individuales.  
  
 Una vez más, recuerde que Visual Basic admite los enfoques imperativo y funcionales, por lo que el mejor diseño para su aplicación podría incorporar elementos de ambos.  
  
## <a name="see-also"></a>Vea también

- [Introducción a las transformaciones funcionales puras (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)
- [Transformación funcional de XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-transformation-of-xml.md)
- [Refactorizar en funciones puras (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md)
