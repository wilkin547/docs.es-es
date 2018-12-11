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
# <a name="configuring-serialization-in-a-workflow-service"></a><span data-ttu-id="45dc0-102">Configurar la serialización en un servicio de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="45dc0-102">Configuring Serialization in a Workflow Service</span></span>
<span data-ttu-id="45dc0-103">Servicios de flujo de trabajo son servicios de Windows Communication Foundation (WCF) y por lo que tiene la opción de utilizar el <xref:System.Runtime.Serialization.DataContractSerializer> (valor predeterminado) o el <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="45dc0-103">Workflow services are Windows Communication Foundation (WCF) services and so have the option of using either the <xref:System.Runtime.Serialization.DataContractSerializer> (the default) or the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="45dc0-104">Cuando se escriben servicios que no son de flujo de trabajo, el tipo de serializados que se va a usar se especifica en el servicio o en el contrato de operación.</span><span class="sxs-lookup"><span data-stu-id="45dc0-104">When writing non-workflow services the type of serializer to use is specified on the service or operation contract.</span></span> <span data-ttu-id="45dc0-105">Al crear servicios de flujo de trabajo WCF no especifican estos contratos en código, pero que se generan en tiempo de ejecución por inferencia del contrato.</span><span class="sxs-lookup"><span data-stu-id="45dc0-105">When creating WCF workflow services you don’t specify these contracts in code, but rather they are generated at runtime by contract inference.</span></span> <span data-ttu-id="45dc0-106">Para obtener más información acerca de la inferencia de contrato, vea [usar contratos en flujo de trabajo](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="45dc0-106">For more information about contract inference, see  [Using Contracts in Workflow](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span></span>  <span data-ttu-id="45dc0-107">El serializador se especifica con la propiedad <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>,</span><span class="sxs-lookup"><span data-stu-id="45dc0-107">The serializer is specified using the <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> property.</span></span> <span data-ttu-id="45dc0-108">que se puede enviar en el diseñador como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="45dc0-108">This can be set in the designer as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="45dc0-109">![Establecer el serializador](../../../../docs/framework/wcf/feature-details/media/settingserialzier.png "SettingSerialzier")</span><span class="sxs-lookup"><span data-stu-id="45dc0-109">![Setting the serializer](../../../../docs/framework/wcf/feature-details/media/settingserialzier.png "SettingSerialzier")</span></span>  
  
 <span data-ttu-id="45dc0-110">El serializador también se puede establecer en código como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="45dc0-110">The serializer can also be set in code as shown in the following example,</span></span>  
  
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
  
 <span data-ttu-id="45dc0-111">Asimismo, los tipos conocidos se pueden especificar en servicios de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="45dc0-111">Known types can be specified on Workflow services as well.</span></span> <span data-ttu-id="45dc0-112">Para obtener más información acerca de los tipos conocidos, consulte [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="45dc0-112">For more information about Known Types see [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span> <span data-ttu-id="45dc0-113">Los tipos conocidos se pueden especificar en el diseñador o en código.</span><span class="sxs-lookup"><span data-stu-id="45dc0-113">Known types can be specified in the designer or in code.</span></span> <span data-ttu-id="45dc0-114">Para especificar tipos conocidos en el diseñador, haga clic en el botón de puntos suspensivos situado junto a la ventana Propiedades de una actividad <xref:System.ServiceModel.Activities.Receive> como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="45dc0-114">To specify known types in the designer, click the ellipsis button next to the KnownTypes property in the properties window for a <xref:System.ServiceModel.Activities.Receive> activity as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="45dc0-115">![Propiedad KnownTypes](../../../../docs/framework/wcf/feature-details/media/knowntypes.png "KnownTypes")</span><span class="sxs-lookup"><span data-stu-id="45dc0-115">![KnownTypes property](../../../../docs/framework/wcf/feature-details/media/knowntypes.png "KnownTypes")</span></span>  
  
 <span data-ttu-id="45dc0-116">De esta forma, se muestra el Editor de colección de tipos que le permitirá buscar y especificar tipos conocidos.</span><span class="sxs-lookup"><span data-stu-id="45dc0-116">This will display the Type Collections Editor that will allow you to search for and specify known types.</span></span>  
  
 <span data-ttu-id="45dc0-117">![Agregar tipos conocidos](../../../../docs/framework/wcf/feature-details/media/typecollectionseditor.gif "TypeCollectionsEditor")</span><span class="sxs-lookup"><span data-stu-id="45dc0-117">![Adding Known Types](../../../../docs/framework/wcf/feature-details/media/typecollectionseditor.gif "TypeCollectionsEditor")</span></span>  
  
 <span data-ttu-id="45dc0-118">Haga clic en el **Agregar nuevo tipo** vínculo y use la lista desplegable para seleccionar o buscar un tipo para agregar a la colección de tipos conocidos.</span><span class="sxs-lookup"><span data-stu-id="45dc0-118">Click the **Add new type** link and use the drop down to select or search for a type to add to the known types collection.</span></span> <span data-ttu-id="45dc0-119">Para especificar los tipos conocidos en código use la propiedad <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="45dc0-119">To specify known types in code use the <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> property as shown in the following example.</span></span>  
  
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
