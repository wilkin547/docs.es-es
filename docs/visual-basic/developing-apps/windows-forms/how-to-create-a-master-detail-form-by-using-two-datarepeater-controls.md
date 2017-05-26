---
title: "Cómo: crear un formulario principal-detalle mediante dos controles DataRepeater (Visual Studio) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 23789bb11cab17b50928651e1dc00d5d59640c0f
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a>Cómo: Crear un formulario principal-detalle mediante dos controles DataRepeater (Visual Studio)
Puede mostrar datos relacionados mediante dos o más <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controles para crear un formulario principal-detalle.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Por ejemplo, desea mostrar una lista de clientes en una <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>y cuando el usuario selecciona un cliente, mostrar una lista de pedidos del cliente en un segundo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
 Puede mostrar datos relacionados arrastrando elementos de detalle que comparten el mismo nodo de tabla principal desde la **orígenes de datos** ventana hasta un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Por ejemplo, si tiene un origen de datos que tiene una tabla clientes y una tabla relacionada Orders, vea ambas tablas como nodos de nivel superior en la vista de árbol en el **orígenes de datos** ventana. Expanda el nodo de los clientes para que pueda ver las columnas. Observe que la última columna de la lista es un nodo expansible que representa la tabla Orders. Este nodo representa los pedidos relacionados para un cliente.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a>Para mostrar datos relacionados en dos controles DataRepeater  
  
1.  Arrastre dos <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controla desde el **Visual Basic PowerPacks** ficha en el **cuadro de herramientas** a un control de formulario o contenedor.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
2.  Arrastre los controladores de tamaño y posición para cambiar el tamaño de los controles y colocarlos en paralelo.  
  
3.  En el menú **Datos** , haga clic en **Mostrar orígenes de datos**.  
  
    > [!NOTE]
    >  Si el **orígenes de datos** ventana está vacía, agregue un origen de datos a él. Para obtener más información, consulte [agregar nuevos orígenes de datos](https://docs.microsoft.com/visualstudio/data-tools/add-new-data-sources).  
  
4.  En el **orígenes de datos** ventana, seleccione el nodo de nivel superior de la tabla principal.  
  
5.  Cambie el tipo drop de la tabla principal a detalles haciendo clic en **detalles** en la lista desplegable en el nodo de tabla.  
  
6.  Arrastre el nodo de tabla principal a la región de la plantilla de elementos de la primera <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
7.  Expanda el nodo de tabla principal y seleccione el nodo de detalle de la tabla relacionada.  
  
8.  Cambie el tipo drop de la tabla de detalle a detalles haciendo clic en **detalles** en la lista desplegable en el nodo de tabla.  
  
9. Seleccione este nodo de tabla y arrástrelo a la región de la plantilla de elementos del segundo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Introducción al Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Cómo: mostrar los datos enlazados en un Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)   
 [Cómo: mostrar relacionados con la aplicación de datos en Windows Forms](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)   
 [Cómo: cambiar la apariencia de un Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
