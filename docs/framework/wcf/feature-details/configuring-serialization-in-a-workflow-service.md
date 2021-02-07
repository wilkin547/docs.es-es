---
description: Más información acerca de cómo configurar la serialización en un servicio de flujo de trabajo
title: Configurar la serialización en un servicio de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: e268f82fc3c1f65086e3c6b112e481ad8abed070
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743244"
---
# <a name="configuring-serialization-in-a-workflow-service"></a>Configurar la serialización en un servicio de flujo de trabajo

Los servicios de flujo de trabajo son servicios de Windows Communication Foundation (WCF) y, por lo tanto, tienen la opción de usar <xref:System.Runtime.Serialization.DataContractSerializer> (el valor predeterminado) o <xref:System.Xml.Serialization.XmlSerializer> . Cuando se escriben servicios que no son de flujo de trabajo, el tipo de serializados que se va a usar se especifica en el servicio o en el contrato de operación. Cuando se crean servicios de flujo de trabajo WCF, no se especifican estos contratos en el código, sino que se generan en tiempo de ejecución por inferencia de contrato. Para obtener más información sobre la inferencia de contratos, vea  [usar contratos en el flujo de trabajo](using-contracts-in-workflow.md).  El serializador se especifica con la propiedad <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>, que se puede enviar en el diseñador como se muestra en la siguiente ilustración.  
  
 ![Establecer la propiedad SerializerOption en la ventana Propiedades.](./media/configuring-serialization-in-a-workflow-service/setting-serializer-property.png)  
  
 El serializador también se puede establecer en código como se muestra en el siguiente ejemplo.  
  
```csharp  
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
```  
  
  Asimismo, los tipos conocidos se pueden especificar en servicios de flujo de trabajo. Para obtener más información sobre los tipos conocidos, consulte [Data Contract known Types](data-contract-known-types.md). Los tipos conocidos se pueden especificar en el diseñador o en código. Para especificar los tipos conocidos en el diseñador, haga clic en el botón de puntos suspensivos junto a la propiedad KnownTypes en la **ventana Propiedades** de una <xref:System.ServiceModel.Activities.Receive> actividad, tal como se muestra en la siguiente ilustración.
  
 ![Captura de pantalla del cuadro de diálogo de la propiedad KnownTypes.](./media/configuring-serialization-in-a-workflow-service/known-types-properties.png)  
  
 Esto muestra el editor de colecciones de tipos que permite buscar y especificar tipos conocidos.  
  
 ![Captura de pantalla del editor de colecciones de tipos.](./media/configuring-serialization-in-a-workflow-service/type-collection-editor.gif)  
  
 Haga clic en el vínculo **Agregar nuevo tipo** y use la lista desplegable para seleccionar o buscar un tipo para agregarlo a la colección de tipos conocidos. Para especificar los tipos conocidos en código use la propiedad <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> como se muestra en el siguiente ejemplo.  
  
```csharp
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
            approveExpense.KnownTypes.Add(typeof(Travel));  
            approveExpense.KnownTypes.Add(typeof(Meal));  
```
