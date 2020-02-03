---
title: Enlazar el control a un objeto de generador
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], binding
- factory objects [Windows Forms], binding to
- BindingSource component [Windows Forms], binding to a factory object
- BindingSource component [Windows Forms], examples
ms.assetid: 7d59af89-ff82-41d8-a48a-f1fbae788b0d
ms.openlocfilehash: 2b4d9aca3345a0cb1e7e995f66a8982dee983ca8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745096"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-factory-object"></a>Cómo: Enlazar un control de Windows Forms a un objeto Factory
Al crear controles que interactúan con datos, a veces considerará necesario enlazar un control a un objeto o un método que genere otros objetos. Este tipo de objetos o métodos se denomina generador. El origen de datos podría ser, por ejemplo, el valor devuelto de una llamada al método, en lugar de un objeto en la memoria o un tipo. Puede enlazar un control a este tipo de origen de datos mientras el origen devuelve una colección.  
  
 Puede enlazar fácilmente un control a un objeto de generador utilizando el control <xref:System.Windows.Forms.BindingSource>.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo enlazar un control <xref:System.Windows.Forms.DataGridView> a un método de generador mediante el uso de un control <xref:System.Windows.Forms.BindingSource>. El método de generador se denomina `GetOrdersByCustomerId` y devuelve todos los pedidos de un cliente determinado en la base de datos Northwind.  
  
 [!code-cpp[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Componente BindingSource](bindingsource-component.md)
- [Cómo: Enlazar un control de Windows Forms a un tipo](how-to-bind-a-windows-forms-control-to-a-type.md)
