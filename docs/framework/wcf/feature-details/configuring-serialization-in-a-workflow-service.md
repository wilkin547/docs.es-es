---
title: Configurar la serialización en un servicio de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: 5076f3d377a656cb96909cf8df01591dc6ab72b7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597545"
---
# <a name="configuring-serialization-in-a-workflow-service"></a><span data-ttu-id="395b0-102">Configurar la serialización en un servicio de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="395b0-102">Configuring Serialization in a Workflow Service</span></span>
<span data-ttu-id="395b0-103">Los servicios de flujo de trabajo son servicios de Windows Communication Foundation (WCF) y, por lo tanto, tienen la opción de usar <xref:System.Runtime.Serialization.DataContractSerializer> (el valor predeterminado) o <xref:System.Xml.Serialization.XmlSerializer> .</span><span class="sxs-lookup"><span data-stu-id="395b0-103">Workflow services are Windows Communication Foundation (WCF) services and so have the option of using either the <xref:System.Runtime.Serialization.DataContractSerializer> (the default) or the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="395b0-104">Cuando se escriben servicios que no son de flujo de trabajo, el tipo de serializados que se va a usar se especifica en el servicio o en el contrato de operación.</span><span class="sxs-lookup"><span data-stu-id="395b0-104">When writing non-workflow services the type of serializer to use is specified on the service or operation contract.</span></span> <span data-ttu-id="395b0-105">Cuando se crean servicios de flujo de trabajo WCF, no se especifican estos contratos en el código, sino que se generan en tiempo de ejecución por inferencia de contrato.</span><span class="sxs-lookup"><span data-stu-id="395b0-105">When creating WCF workflow services you don’t specify these contracts in code, but rather they are generated at runtime by contract inference.</span></span> <span data-ttu-id="395b0-106">Para obtener más información sobre la inferencia de contratos, vea [usar contratos en el flujo de trabajo](using-contracts-in-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="395b0-106">For more information about contract inference, see  [Using Contracts in Workflow](using-contracts-in-workflow.md).</span></span>  <span data-ttu-id="395b0-107">El serializador se especifica con la propiedad <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>,</span><span class="sxs-lookup"><span data-stu-id="395b0-107">The serializer is specified using the <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> property.</span></span> <span data-ttu-id="395b0-108">que se puede enviar en el diseñador como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="395b0-108">This can be set in the designer as shown in the following illustration.</span></span>  
  
 ![Establecer la propiedad SerializerOption en la ventana Propiedades.](./media/configuring-serialization-in-a-workflow-service/setting-serializer-property.png)  
  
 <span data-ttu-id="395b0-110">El serializador también se puede establecer en código como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="395b0-110">The serializer can also be set in code as shown in the following example,</span></span>  
  
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
  
  <span data-ttu-id="395b0-111">Asimismo, los tipos conocidos se pueden especificar en servicios de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="395b0-111">Known types can be specified on Workflow services as well.</span></span> <span data-ttu-id="395b0-112">Para obtener más información sobre los tipos conocidos, consulte [Data Contract known Types](data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="395b0-112">For more information about Known Types, see [Data Contract Known Types](data-contract-known-types.md).</span></span> <span data-ttu-id="395b0-113">Los tipos conocidos se pueden especificar en el diseñador o en código.</span><span class="sxs-lookup"><span data-stu-id="395b0-113">Known types can be specified in the designer or in code.</span></span> <span data-ttu-id="395b0-114">Para especificar los tipos conocidos en el diseñador, haga clic en el botón de puntos suspensivos junto a la propiedad KnownTypes en la **ventana Propiedades** de una <xref:System.ServiceModel.Activities.Receive> actividad, tal como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="395b0-114">To specify known types in the designer, click the ellipsis button next to the KnownTypes property in the **Properties Window** for a <xref:System.ServiceModel.Activities.Receive> activity as shown in the following illustration.</span></span>
  
 ![Captura de pantalla del cuadro de diálogo de la propiedad KnownTypes.](./media/configuring-serialization-in-a-workflow-service/known-types-properties.png)  
  
 <span data-ttu-id="395b0-116">Esto muestra el editor de colecciones de tipos que permite buscar y especificar tipos conocidos.</span><span class="sxs-lookup"><span data-stu-id="395b0-116">This displays the Type Collections Editor that allows you to search for and specify known types.</span></span>  
  
 ![Captura de pantalla del editor de colecciones de tipos.](./media/configuring-serialization-in-a-workflow-service/type-collection-editor.gif)  
  
 <span data-ttu-id="395b0-118">Haga clic en el vínculo **Agregar nuevo tipo** y use la lista desplegable para seleccionar o buscar un tipo para agregarlo a la colección de tipos conocidos.</span><span class="sxs-lookup"><span data-stu-id="395b0-118">Click the **Add new type** link and use the drop down to select or search for a type to add to the known types collection.</span></span> <span data-ttu-id="395b0-119">Para especificar los tipos conocidos en código use la propiedad <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="395b0-119">To specify known types in code use the <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> property as shown in the following example.</span></span>  
  
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
