---
title: Diferencias entre la programación funcional y Programación imperativa
ms.date: 07/20/2015
ms.assetid: 6a1f3b57-00e6-447d-9906-74c7c4d5d85c
ms.openlocfilehash: 0090761dc07218673e1e0299951530d5a4763ffe
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84364804"
---
# <a name="functional-programming-vs-imperative-programming-visual-basic"></a>Programación funcional frente a programación imperativa (Visual Basic)
Este tema compara y contrasta la programación funcional y la programación imperativa (orientada a procedimientos) más tradicional.  
  
## <a name="functional-programming-vs-imperative-programming"></a>Diferencias entre la programación funcional y Programación imperativa  
 El paradigma de la *programación funcional* se ha creado explícitamente para permitir un enfoque puramente funcional de la resolución de problemas. La programación funcional es una forma de *programación declarativa*. Por el contrario, la mayoría de lenguajes más populares, incluidos los lenguajes de programación orientada a objetos (OOP) como C#, Visual Basic, C++ y Java, se han diseñado para admitir en primer lugar la programación *imperativa* (orientada a procedimientos).  
  
 El enfoque imperativo permite al desarrollador escribir código que describe detalladamente los pasos que el equipo debe realizar para cumplir el objetivo. A veces también se denomina programación *algorítmica*. Por el contrario, un enfoque funcional implica crear el problema como un conjunto de funciones que se deben ejecutar. Es necesario definir con cuidado la entrada a cada función y qué devuelve cada función. La siguiente tabla describe algunas de las diferencias generales entre estos dos enfoques.  
  
|Característica|Enfoque imperativo|Enfoque funcional|  
|--------------------|-------------------------|-------------------------|  
|Enfoque del programador|Cómo realizar tareas (algoritmos) y cómo realizar el seguimiento de cambios de estado.|Información deseada y transformaciones necesarias|  
|Cambios de estado|Importante|Inexistente|  
|Orden de ejecución|Importante|Baja importancia|  
|Control del flujo primario|Bucles, elementos condicionales y llamadas a funciones (métodos).|Llamadas a funciones, incluyendo la recursividad.|  
|Unidad de manipulación primaria|Instancias de estructuras o clases|Funciones como recopilaciones de datos y objetos de primera clase|  
  
 Aunque la mayoría de lenguajes se diseñaron para admitir un paradigma de programación específico, muchos lenguajes generales son lo suficientemente flexibles para admitir varios paradigmas. Por ejemplo, la mayoría de los lenguajes que contienen punteros a funciones se pueden usar para permitir de forma creíble la programación funcional. Además, Visual Basic incluye extensiones de lenguaje explícitas para admitir la programación funcional, incluidas las expresiones lambda y la inferencia de tipos. La tecnología LINQ es una forma de programación funcional y declarativa.  
  
## <a name="functional-programming-using-xslt"></a>Programación funcional con XSLT  
 Muchos desarrolladores de XSLT están familiarizados con el enfoque funcional puro. La forma más eficaz de desarrollar una hoja de estilos XSLT es tratar cada plantilla como una transformación de componentes aislada. El orden de ejecución no está realzado. XSLT no admite efectos secundarios (excepto cuando mecanismos de escape para ejecutar código de procedimiento puedan provocar efectos secundarios, cuyo resultado es una impureza funcional). Sin embargo, a pesar de que XSLT es una herramienta eficaz, algunas de sus características no son óptimas. Por ejemplo, cuando se expresan construcciones de programación en XML se obtiene un código relativamente detallado y, por lo tanto, difícil de mantener. Asimismo, la gran dependencia de la repetición para el control de flujo puede provocar que el código sea difícil de leer. Para obtener más información sobre XSLT, vea [Transformaciones XSLT](../../../../standard/data/xml/xslt-transformations.md).  
  
 No obstante, XSLT ha demostrado el valor de usar un enfoque funcional puro para transformar XML de una forma a otra. La programación funcional pura con LINQ to XML es muy parecida a XSLT. Sin embargo, las construcciones de programación introducidas por LINQ to XML y Visual Basic permiten escribir transformaciones funcionales puras que son más legibles y se pueden mantener que XSLT.  
  
## <a name="advantages-of-pure-functions"></a>Ventajas de las funciones puras  
 El motivo principal para implementar transformaciones funcionales como funciones puras es que las funciones puras son ajustables: es decir, independientes y sin estado. Estas características aportan varias ventajas, incluyendo las siguientes:  
  
- Mayor legibilidad y facilidad de mantenimiento. Esto se debe a que cada función está diseñada para cumplir una tarea específica dependiendo de sus argumentos. Esta función no depende de ningún estado externo.  
  
- Desarrollo reiterativo más sencillo. Como es más sencillo refactorizar el código, la implementación de los cambios de diseño resulta a menudo más fácil. Por ejemplo, supongamos que escribe una transformación complicada y después se da cuenta de que parte del código se repite varias veces en la transformación. Si refactoriza mediante un método puro, puede llamar a su método puro cuando lo desee sin preocuparse de efectos secundarios.  
  
- Pruebas y depuraciones más sencillas. Como las funciones puras se pueden probar más fácilmente en aislamiento, puede escribir código de prueba que llame a la función pura con valores típicos, casos avanzados válidos y casos avanzados no válidos.  
  
## <a name="transitioning-for-oop-developers"></a>Transición para desarrolladores de OOP  
 En la programación orientada a objetos (OOP) tradicional, la mayoría de desarrolladores están acostumbrados a programar en estilo imperativo/de procedimientos. Para pasar al desarrollo en un estilo funcional puro, tienen que realizar una transición en su forma de pensar y en su planteamiento del desarrollo.  
  
 Para solucionar problemas, los desarrolladores de OOP diseñan jerarquías de clases, se centran en la correcta encapsulación y piensan en términos de contratos de clase. El comportamiento y el estado de los tipos de objetos son de vital importancia y las características del lenguaje, como las clases, las interfaces, la herencia y el polimorfismo se proporcionan para tratar estas preocupaciones.  
  
 Por el contrario, la programación funcional considera los problemas de cálculo como un ejercicio de evaluación de transformaciones funcionales puras de recopilaciones de datos. La programación funcional evita datos mutables y de estado, y pone de relieve, en su lugar, la aplicación de las funciones.  
  
 Afortunadamente, Visual Basic no requiere un salto completo a la programación funcional, ya que admite enfoques de programación imperativos y funcionales. Un desarrollador puede elegir el enfoque más adecuado para una escenario específico. En realidad, los programas suelen combinar ambos enfoques.  
  
## <a name="see-also"></a>Vea también

- [Introducción a las transformaciones funcionales puras (Visual Basic)](introduction-to-pure-functional-transformations.md)
- [Transformaciones XSLT](../../../../standard/data/xml/xslt-transformations.md)
- [Refactorizar en funciones puras (Visual Basic)](refactoring-into-pure-functions.md)
