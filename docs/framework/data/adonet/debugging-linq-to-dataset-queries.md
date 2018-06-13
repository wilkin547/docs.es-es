---
title: Depurar consultas de LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: f4c54015-8ce2-4c5c-8d18-7038144cc66d
ms.openlocfilehash: c0d3347358fa3417f8b73fd848b4091fe7d74a15
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760120"
---
# <a name="debugging-linq-to-dataset-queries"></a>Depurar consultas de LINQ to DataSet
[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] permite depurar el código [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. Sin embargo, existen algunas diferencias entre depurar código [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]  y depurar código administrado que no es [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. La mayor parte de las características de depuración funcionan con instrucciones [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], entre ellas la función de examen, de establecimiento de puntos de interrupción y el examen de resultados que se muestran en la ventana del depurador. Sin embargo, la consultas diferido ejecución en conlleva algunos efectos secundarios que debe tener en cuenta durante la depuración [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] de código y hay algunas limitaciones para utilizar editar y continuar. En este tema se trata aspectos de depuración únicos para [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] en comparación con la que no son[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] código administrado.  
  
## <a name="viewing-results"></a>Ver los resultados  
 Puede ver el resultado de una [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] instrucción mediante información sobre datos, la ventana Inspección y cuadro de diálogo Inspección rápida. Al usar una ventana de código fuente, puede pausar el puntero en una consulta en la ventana de código fuente para que aparezca una información sobre datos. Puede copiar una variable [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] y pegarla en la ventana Inspección o en el cuadro de diálogo Inspección rápida. En [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], una consulta no se evalúa cuando se crea o declara, pero únicamente cuando se ejecuta. Esto se denomina *ejecución diferida*. Por consiguiente, la variable de consulta no tiene un valor hasta que se evalúe. Para obtener más información, consulte [las consultas LINQ to DataSet](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md).  
  
 Para mostrar el resultado de una consulta, el depurador debe evaluarla. Esta evaluación implícita se produce cuando se ve un [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] resultado de la consulta en el depurador y tiene algunos efectos que debería considerar. Cada evaluación de la consulta lleva tiempo. Expandir el nodo de resultados lleva tiempo. Para algunas consultas, la evaluación repetida podría producir una reducción notable del rendimiento. Evaluar una consulta también puede producir efectos secundarios, que son cambios en el valor de los datos o en el estado del programa. No todas las consultas tienen los efectos secundarios. Para determinar si una consulta se puede evaluar sin ningún riesgo ni efectos secundarios, debe entender el código que implementa la consulta. Para obtener más información, consulte [expresiones y efectos secundarios](http://msdn.microsoft.com/library/e1f8a6ea-9e19-481d-b6bd-df120ad3bf4e).  
  
## <a name="edit-and-continue"></a>Editar y continuar  
 Editar y continuar no admite cambios en [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] las consultas. Si agregar, quitar o cambiar una [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] aparece un cuadro de diálogo de instrucción durante una sesión de depuración, que indica el cambio no es compatible con Editar y continuar. En ese momento, puede deshacer los cambios o detener la sesión de depuración y reiniciar una nueva sesión con el código revisado.  
  
 Además, editar y continuar no permite cambiar el tipo o el valor de una variable que se utiliza en un [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] instrucción. De nuevo, puede deshacer los cambios o detener y reiniciar la sesión de depuración.  
  
 En Visual C# en Visual Studio, no puede usar Editar y continuar en cualquier código en un método que contiene un [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] consulta.  
  
 En Visual Basic en Visual Studio, puede usar Editar y continuar no-[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] código, incluso en un método que contiene un [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] consulta. Puede agregar o quitar el código antes del [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] instrucción, incluso si los cambios afectan al número de línea de la [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] consulta. Experiencia de depuración de Visual Basic no es[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] código sigue siendo el mismo que estaba antes [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] introducida. No se puede cambiar, agregar o quitar un [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] consulten, sin embargo, a menos que se detiene la depuración para aplicar los cambios.  
  
## <a name="see-also"></a>Vea también  
 [Depurar código administrado](/visualstudio/debugger/debugging-managed-code)  
 [Guía de programación](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
