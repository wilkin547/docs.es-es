---
title: "Aplicabilidad de la transformación funcional (C#) | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: c78107bd-b006-4574-a3d4-bbf808388ff3
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0f79ec1e5975a1197464785182a7e6d4af4ba61c
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017


---
# <a name="applicability-of-functional-transformation-c"></a>Aplicabilidad de la transformación funcional (C#)
Las transformaciones funcionales puras se pueden aplicar en una amplia variedad de situaciones.  
  
 El enfoque de transformación funcional es especialmente adecuado para consultar y manipular datos estructurados; por lo tanto encaja bien con las tecnologías LINQ. No obstante, la transformación funcional tiene una aplicabilidad mucho más amplia que el uso con LINQ. Cualquier proceso en el que el centro de atención principal sea la transformación de datos de un formato a otro probablemente debe considerarse un candidato para la transformación funcional.  
  
 Este enfoque es aplicable a muchos problemas que a primera vista pueden no parecer candidatos. La transformación funcional, usada en conjunción con o de forma separada de LINQ, debe tenerse en cuenta para las siguientes áreas:  
  
-   Documentos basados en XML. Los datos bien formados de cualquier dialecto XML se pueden manipular fácilmente mediante la transformación funcional. Para obtener más información, consulte [Functional Transformation of XML (C#)](../../../../csharp/programming-guide/concepts/linq/functional-transformation-of-xml.md) (Transformación funcional de XML [C#]).  
  
-   Otros formatos de archivo estructurados. Desde archivos Windows.ini a documentos de texto sin formato, la mayoría de archivos tienen alguna estructura que se presta a análisis y transformación.  
  
-   Protocolos de secuencia de datos. La codificación y decodificación de datos de protocolos de comunicación a menudo se puede representar con una sencilla transformación funcional.  
  
-   Datos RDBMS y OODBMS. Las bases de datos relacionales y orientadas a objetos, como XML, son orígenes de datos estructurados muy utilizados.  
  
-   Soluciones científicas, estadísticas y matemáticas. Estos campos suelen manipular grandes cantidades de datos para ayudar al usuario a visualizar, estimar o resolver problemas que no son triviales.  
  
 Como se describe en [Refactorizar en funciones puras (C#)](../../../../csharp/programming-guide/concepts/linq/refactoring-into-pure-functions.md), el uso de funciones puras es un ejemplo de programación funcional. Además de sus ventajas inmediatas, el uso de funciones puras proporciona una valiosa experiencia para la resolución de problemas desde una perspectiva de transformación funcional. Este enfoque también puede tener un gran impacto en el diseño de clases y la programación. Éste es el caso cuando un problema se presta a una solución de transformación de datos tal como se ha escrito anteriormente.  
  
 Aunque quedan fuera del ámbito de este tutorial, los diseños que tienen la influencia de la perspectiva de transformación funcional tienden a centrarse en procesos más que en objetos como actores y la solución resultante tiende a implementarse como una serie de transformaciones a gran escala en lugar de cambios de estado de objeto individuales.  
  
 Una vez más, no olvide que C# admite los enfoques imperativo y funcional, por lo que el mejor diseño para su aplicación podría incorporar elementos de ambos.  
  
## <a name="see-also"></a>Vea también  
 [Introducción a las transformaciones funcionales puras (C#)](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)   
 [Functional Transformation of XML (C#)](../../../../csharp/programming-guide/concepts/linq/functional-transformation-of-xml.md)  (Transformación funcional de XML [C#])  
 [Refactorizar en funciones puras (C#)](../../../../csharp/programming-guide/concepts/linq/refactoring-into-pure-functions.md)
