---
title: Configurar la serialización en un servicio de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: f894f2e044e35bb278f975ef2385a6b22a8bea49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185344"
---
# <a name="configuring-serialization-in-a-workflow-service"></a>Configurar la serialización en un servicio de flujo de trabajo
Los servicios de flujo de trabajo son servicios de Windows <xref:System.Runtime.Serialization.DataContractSerializer> Communication Foundation (WCF) y, por lo tanto, tienen la opción de usar el archivo (valor predeterminado) o el <xref:System.Xml.Serialization.XmlSerializer>archivo . Cuando se escriben servicios que no son de flujo de trabajo, el tipo de serializados que se va a usar se especifica en el servicio o en el contrato de operación. Al crear servicios de flujo de trabajo WCF no se especifican estos contratos en el código, sino que se generan en tiempo de ejecución por inferencia de contrato. Para obtener más información acerca de la inferencia de contratos, consulte Uso de [contratos en flujo](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md)de trabajo .  El serializador se especifica con la propiedad <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>, que se puede enviar en el diseñador como se muestra en la siguiente ilustración.  
  
 ![Establecer el SerializerOption propiedad en el propiedades ventana.](./media/configuring-serialization-in-a-workflow-service/setting-serializer-property.png)  
  
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
  
  Asimismo, los tipos conocidos se pueden especificar en servicios de flujo de trabajo. Para obtener más información acerca de los tipos conocidos, vea [Tipos conocidos](data-contract-known-types.md)de contrato de datos . Los tipos conocidos se pueden especificar en el diseñador o en código. Para especificar tipos conocidos en el diseñador, haga clic en el botón de puntos suspensivos situado junto a la propiedad KnownTypes de la **ventana Propiedades** de una <xref:System.ServiceModel.Activities.Receive> actividad, como se muestra en la siguiente ilustración.
  
 ![Captura de pantalla del cuadro de diálogo de la propiedad KnownTypes.](./media/configuring-serialization-in-a-workflow-service/known-types-properties.png)  
  
 Esto muestra el Editor de colecciones de tipos que le permite buscar y especificar tipos conocidos.  
  
 ![Captura de pantalla del Editor de colecciones de tipos.](./media/configuring-serialization-in-a-workflow-service/type-collection-editor.gif)  
  
 Haga clic en el vínculo **Agregar nuevo tipo** y use el menú desplegable para seleccionar o buscar un tipo para agregarlo a la colección de tipos conocidos. Para especificar los tipos conocidos en código use la propiedad <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> como se muestra en el siguiente ejemplo.  
  
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
