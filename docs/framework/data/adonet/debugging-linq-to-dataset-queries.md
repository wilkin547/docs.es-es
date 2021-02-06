---
description: Más información acerca de cómo depurar consultas LINQ to DataSet
title: Depurar consultas de LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: f4c54015-8ce2-4c5c-8d18-7038144cc66d
ms.openlocfilehash: f1293ba195c96d6868fdd5bfee50e8734f9cecc4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651228"
---
# <a name="debugging-linq-to-dataset-queries"></a>Depurar consultas de LINQ to DataSet

Visual Studio admite la depuración de código de LINQ to DataSet. Sin embargo, hay algunas diferencias entre la depuración de código LINQ to DataSet y el código no LINQ to DataSet administrado. La mayoría de las características de depuración funcionan con instrucciones de LINQ to DataSet, incluida la ejecución paso a paso, el establecimiento de puntos de interrupción y la visualización de resultados que se muestran en ventanas del depurador. Sin embargo, la ejecución de consultas diferida en tiene algunos efectos secundarios que se deben tener en cuenta durante la depuración LINQ to DataSet código y existen algunas limitaciones en el uso de editar y continuar. En este tema se tratan aspectos de la depuración que son únicos en LINQ to DataSet comparados con el código no LINQ to DataSet administrado.  
  
## <a name="viewing-results"></a>Ver los resultados  

 Puede ver el resultado de una instrucción LINQ to DataSet mediante información sobre herramientas, el ventana Inspección y el cuadro de diálogo Inspección rápida. Al usar una ventana de código fuente, puede pausar el puntero en una consulta en la ventana de código fuente para que aparezca una información sobre datos. Puede copiar una variable de LINQ to DataSet y pegarla en el ventana Inspección o en el cuadro de diálogo Inspección rápida. En LINQ to DataSet, una consulta no se evalúa cuando se crea o declara, pero solo cuando se ejecuta la consulta. Esto se denomina *ejecución aplazada*. Por consiguiente, la variable de consulta no tiene un valor hasta que se evalúe. Para obtener más información, vea [consultas en LINQ to DataSet](queries-in-linq-to-dataset.md).  
  
 Para mostrar el resultado de una consulta, el depurador debe evaluarla. Esta evaluación implícita se produce cuando se ve un LINQ to DataSet resultado de la consulta en el depurador y tiene algunos efectos que se deben tener en cuenta. Cada evaluación de la consulta lleva tiempo. Expandir el nodo de resultados lleva tiempo. Para algunas consultas, la evaluación repetida podría producir una reducción notable del rendimiento. Evaluar una consulta también puede producir efectos secundarios, que son cambios en el valor de los datos o en el estado del programa. No todas las consultas tienen los efectos secundarios. Para determinar si una consulta se puede evaluar sin ningún riesgo ni efectos secundarios, debe entender el código que implementa la consulta. Para obtener más información, vea [efectos secundarios y expresiones](/previous-versions/visualstudio/visual-studio-2013/a7a250bs(v=vs.120)).  
  
## <a name="edit-and-continue"></a>Editar y continuar  

 Editar y continuar no admite cambios en las consultas de LINQ to DataSet. Si agrega, quita o cambia una instrucción LINQ to DataSet durante una sesión de depuración, aparece un cuadro de diálogo que indica que el cambio no es compatible con editar y continuar. En ese momento, puede deshacer los cambios o detener la sesión de depuración y reiniciar una nueva sesión con el código revisado.  
  
 Además, editar y continuar no permite cambiar el tipo o el valor de una variable que se usa en una instrucción LINQ to DataSet. De nuevo, puede deshacer los cambios o detener y reiniciar la sesión de depuración.  
  
 En Visual C# en Visual Studio, no puede usar editar y continuar en cualquier código en un método que contenga una consulta LINQ to DataSet.  
  
 En Visual Basic en Visual Studio, puede usar editar y continuar en código no LINQ to DataSet, incluso en un método que contenga una consulta LINQ to DataSet. Puede Agregar o quitar código antes de la instrucción LINQ to DataSet, incluso si los cambios afectan al número de línea de la consulta LINQ to DataSet. La experiencia de depuración de Visual Basic para el código que no es de LINQ to DataSet sigue siendo la misma que antes de que se introdujera LINQ to DataSet. Sin embargo, no se puede cambiar, agregar o quitar una consulta LINQ to DataSet, a menos que se detenga la depuración para aplicar los cambios.  
  
## <a name="see-also"></a>Vea también

- [Depurar código administrado](/visualstudio/debugger/debugging-managed-code)
- [Guía de programación](programming-guide-linq-to-dataset.md)
