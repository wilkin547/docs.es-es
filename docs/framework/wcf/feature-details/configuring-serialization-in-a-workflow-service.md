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
# <a name="configuring-serialization-in-a-workflow-service"></a><span data-ttu-id="a5f3f-102">Configurar la serialización en un servicio de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a5f3f-102">Configuring Serialization in a Workflow Service</span></span>
<span data-ttu-id="a5f3f-103">Los servicios de flujo de trabajo son servicios de Windows <xref:System.Runtime.Serialization.DataContractSerializer> Communication Foundation (WCF) y, por lo tanto, tienen la opción de usar el archivo (valor predeterminado) o el <xref:System.Xml.Serialization.XmlSerializer>archivo .</span><span class="sxs-lookup"><span data-stu-id="a5f3f-103">Workflow services are Windows Communication Foundation (WCF) services and so have the option of using either the <xref:System.Runtime.Serialization.DataContractSerializer> (the default) or the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="a5f3f-104">Cuando se escriben servicios que no son de flujo de trabajo, el tipo de serializados que se va a usar se especifica en el servicio o en el contrato de operación.</span><span class="sxs-lookup"><span data-stu-id="a5f3f-104">When writing non-workflow services the type of serializer to use is specified on the service or operation contract.</span></span> <span data-ttu-id="a5f3f-105">Al crear servicios de flujo de trabajo WCF no se especifican estos contratos en el código, sino que se generan en tiempo de ejecución por inferencia de contrato.</span><span class="sxs-lookup"><span data-stu-id="a5f3f-105">When creating WCF workflow services you don’t specify these contracts in code, but rather they are generated at runtime by contract inference.</span></span> <span data-ttu-id="a5f3f-106">Para obtener más información acerca de la inferencia de contratos, consulte Uso de [contratos en flujo](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md)de trabajo .</span><span class="sxs-lookup"><span data-stu-id="a5f3f-106">For more information about contract inference, see  [Using Contracts in Workflow](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span></span>  <span data-ttu-id="a5f3f-107">El serializador se especifica con la propiedad <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>,</span><span class="sxs-lookup"><span data-stu-id="a5f3f-107">The serializer is specified using the <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> property.</span></span> <span data-ttu-id="a5f3f-108">que se puede enviar en el diseñador como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="a5f3f-108">This can be set in the designer as shown in the following illustration.</span></span>  
  
 ![Establecer el SerializerOption propiedad en el propiedades ventana.](./media/configuring-serialization-in-a-workflow-service/setting-serializer-property.png)  
  
 <span data-ttu-id="a5f3f-110">El serializador también se puede establecer en código como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a5f3f-110">The serializer can also be set in code as shown in the following example,</span></span>  
  
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
  
  <span data-ttu-id="a5f3f-111">Asimismo, los tipos conocidos se pueden especificar en servicios de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a5f3f-111">Known types can be specified on Workflow services as well.</span></span> <span data-ttu-id="a5f3f-112">Para obtener más información acerca de los tipos conocidos, vea [Tipos conocidos](data-contract-known-types.md)de contrato de datos .</span><span class="sxs-lookup"><span data-stu-id="a5f3f-112">For more information about Known Types, see [Data Contract Known Types](data-contract-known-types.md).</span></span> <span data-ttu-id="a5f3f-113">Los tipos conocidos se pueden especificar en el diseñador o en código.</span><span class="sxs-lookup"><span data-stu-id="a5f3f-113">Known types can be specified in the designer or in code.</span></span> <span data-ttu-id="a5f3f-114">Para especificar tipos conocidos en el diseñador, haga clic en el botón de puntos suspensivos situado junto a la propiedad KnownTypes de la **ventana Propiedades** de una <xref:System.ServiceModel.Activities.Receive> actividad, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="a5f3f-114">To specify known types in the designer, click the ellipsis button next to the KnownTypes property in the **Properties Window** for a <xref:System.ServiceModel.Activities.Receive> activity as shown in the following illustration.</span></span>
  
 ![Captura de pantalla del cuadro de diálogo de la propiedad KnownTypes.](./media/configuring-serialization-in-a-workflow-service/known-types-properties.png)  
  
 <span data-ttu-id="a5f3f-116">Esto muestra el Editor de colecciones de tipos que le permite buscar y especificar tipos conocidos.</span><span class="sxs-lookup"><span data-stu-id="a5f3f-116">This displays the Type Collections Editor that allows you to search for and specify known types.</span></span>  
  
 ![Captura de pantalla del Editor de colecciones de tipos.](./media/configuring-serialization-in-a-workflow-service/type-collection-editor.gif)  
  
 <span data-ttu-id="a5f3f-118">Haga clic en el vínculo **Agregar nuevo tipo** y use el menú desplegable para seleccionar o buscar un tipo para agregarlo a la colección de tipos conocidos.</span><span class="sxs-lookup"><span data-stu-id="a5f3f-118">Click the **Add new type** link and use the drop down to select or search for a type to add to the known types collection.</span></span> <span data-ttu-id="a5f3f-119">Para especificar los tipos conocidos en código use la propiedad <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a5f3f-119">To specify known types in code use the <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> property as shown in the following example.</span></span>  
  
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
