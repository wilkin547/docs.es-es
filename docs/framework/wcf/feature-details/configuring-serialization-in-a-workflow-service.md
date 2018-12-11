---
title: Configurar la serialización en un servicio de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: 63a5860bd428fd4ce7fe01d7901427c85b2d5609
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53154117"
---
# <a name="configuring-serialization-in-a-workflow-service"></a>Configurar la serialización en un servicio de flujo de trabajo
Servicios de flujo de trabajo son servicios de Windows Communication Foundation (WCF) y por lo que tiene la opción de utilizar el <xref:System.Runtime.Serialization.DataContractSerializer> (valor predeterminado) o el <xref:System.Xml.Serialization.XmlSerializer>. Cuando se escriben servicios que no son de flujo de trabajo, el tipo de serializados que se va a usar se especifica en el servicio o en el contrato de operación. Al crear servicios de flujo de trabajo WCF no especifican estos contratos en código, pero que se generan en tiempo de ejecución por inferencia del contrato. Para obtener más información acerca de la inferencia de contrato, vea [usar contratos en flujo de trabajo](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).  El serializador se especifica con la propiedad <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>, que se puede enviar en el diseñador como se muestra en la siguiente ilustración.  
  
 ![Establecer el serializador](../../../../docs/framework/wcf/feature-details/media/settingserialzier.png "SettingSerialzier")  
  
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
  
 Asimismo, los tipos conocidos se pueden especificar en servicios de flujo de trabajo. Para obtener más información acerca de los tipos conocidos, consulte [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md). Los tipos conocidos se pueden especificar en el diseñador o en código. Para especificar tipos conocidos en el diseñador, haga clic en el botón de puntos suspensivos situado junto a la ventana Propiedades de una actividad <xref:System.ServiceModel.Activities.Receive> como se muestra en la siguiente ilustración.  
  
 ![Propiedad KnownTypes](../../../../docs/framework/wcf/feature-details/media/knowntypes.png "KnownTypes")  
  
 De esta forma, se muestra el Editor de colección de tipos que le permitirá buscar y especificar tipos conocidos.  
  
 ![Agregar tipos conocidos](../../../../docs/framework/wcf/feature-details/media/typecollectionseditor.gif "TypeCollectionsEditor")  
  
 Haga clic en el **Agregar nuevo tipo** vínculo y use la lista desplegable para seleccionar o buscar un tipo para agregar a la colección de tipos conocidos. Para especificar los tipos conocidos en código use la propiedad <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> como se muestra en el siguiente ejemplo.  
  
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
