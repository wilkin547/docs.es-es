---
title: Configurar la serialización en un servicio de flujo de trabajo
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 47c66077da051fd70300e1961593e906fe8e77aa
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="configuring-serialization-in-a-workflow-service"></a>Configurar la serialización en un servicio de flujo de trabajo
Los servicios de flujo de trabajo son servicios de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y, por tanto, tienen la opción de usar la clase <xref:System.Runtime.Serialization.DataContractSerializer> (el valor predeterminado) o la clase <xref:System.Xml.Serialization.XmlSerializer>. Cuando se escriben servicios que no son de flujo de trabajo, el tipo de serializados que se va a usar se especifica en el servicio o en el contrato de operación. Cuando se crean servicios de flujo de trabajo de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], no se especifican estos contratos en código, sino que se generan en tiempo de ejecución por inferencia de contrato. Para obtener más información acerca de inferencia del contrato, vea [usar contratos en el flujo de trabajo](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).  El serializador se especifica con la propiedad <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>, que se puede enviar en el diseñador como se muestra en la siguiente ilustración.  
  
 ![Configurar el serializador](../../../../docs/framework/wcf/feature-details/media/settingserialzier.png "SettingSerialzier")  
  
 El serializador también se puede establecer en código como se muestra en el siguiente ejemplo.  
  
```  
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
```  
  
 Asimismo, los tipos conocidos se pueden especificar en servicios de flujo de trabajo. Para obtener más información acerca de los tipos conocidos, consulte [tipos conocidos de contrato de datos](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md). Los tipos conocidos se pueden especificar en el diseñador o en código. Para especificar tipos conocidos en el diseñador, haga clic en el botón de puntos suspensivos situado junto a la ventana Propiedades de una actividad <xref:System.ServiceModel.Activities.Receive> como se muestra en la siguiente ilustración.  
  
 ![Propiedad KnownTypes](../../../../docs/framework/wcf/feature-details/media/knowntypes.png "KnownTypes")  
  
 De esta forma, se muestra el Editor de colección de tipos que le permitirá buscar y especificar tipos conocidos.  
  
 ![Agregar tipos conocidos](../../../../docs/framework/wcf/feature-details/media/typecollectionseditor.gif "TypeCollectionsEditor")  
  
 Haga clic en el **Agregar nuevo tipo** vínculo y use la lista desplegable para seleccionar o buscar un tipo para agregar a la colección de tipos conocidos. Para especificar los tipos conocidos en código use la propiedad <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> como se muestra en el siguiente ejemplo.  
  
```  
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
  
 Para ver un ejemplo de código completo que muestra cómo configurar la serialización de un servicio de flujo de trabajo detecta [dar formato a mensajes en los servicios de flujo de trabajo](../../../../docs/framework/windows-workflow-foundation/samples/formatting-messages-in-workflow-services.md).
