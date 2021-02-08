---
description: 'Más información sobre: Cómo: establecer la propiedad ProtectionLevel'
title: Procedimiento para establecer la propiedad ProtectionLevel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, security
- ProtectionLevel property
ms.assetid: 3d4e8f80-0f9e-4a26-9899-beb6584e78df
ms.openlocfilehash: 526ed923d254f0312c9a2c6d17b7306973d88902
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779249"
---
# <a name="how-to-set-the-protectionlevel-property"></a><span data-ttu-id="ce912-103">Procedimiento para establecer la propiedad ProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="ce912-103">How to: Set the ProtectionLevel Property</span></span>

<span data-ttu-id="ce912-104">Puede establecer el nivel de protección aplicando un atributo adecuado y estableciendo la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ce912-104">You can set the protection level by applying an appropriate attribute and setting the property.</span></span> <span data-ttu-id="ce912-105">Puede establecer la protección en el nivel del servicio para que afecte a todas las partes de cada mensaje o puede establecer la protección en los niveles cada vez más individuales, desde los métodos a las partes del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ce912-105">You can set protection at the service level to affect all parts of every message, or you can set protection at increasingly granular levels, from methods to message parts.</span></span> <span data-ttu-id="ce912-106">Para obtener más información acerca de la `ProtectionLevel` propiedad, consulte [Descripción del nivel de protección](understanding-protection-level.md).</span><span class="sxs-lookup"><span data-stu-id="ce912-106">For more information about the `ProtectionLevel` property, see [Understanding Protection Level](understanding-protection-level.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ce912-107">Puede establecer niveles de protección solo mediante código, no mediante configuración.</span><span class="sxs-lookup"><span data-stu-id="ce912-107">You can set protection levels only in code, not in configuration.</span></span>  
  
### <a name="to-sign-all-messages-for-a-service"></a><span data-ttu-id="ce912-108">Para firmar todos los mensajes para un servicio</span><span class="sxs-lookup"><span data-stu-id="ce912-108">To sign all messages for a service</span></span>  
  
1. <span data-ttu-id="ce912-109">Cree una interfaz para el servicio.</span><span class="sxs-lookup"><span data-stu-id="ce912-109">Create an interface for the service.</span></span>  
  
2. <span data-ttu-id="ce912-110">Aplique el atributo <xref:System.ServiceModel.ServiceContractAttribute> al servicio y establezca la propiedad <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> en <xref:System.Net.Security.ProtectionLevel.Sign>, como se muestra en el código siguiente (el nivel predeterminado es <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>).</span><span class="sxs-lookup"><span data-stu-id="ce912-110">Apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the service and set the <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> property to <xref:System.Net.Security.ProtectionLevel.Sign>, as shown in the following code (the default level is <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>).</span></span>  
  
     [!code-csharp[C_ProtectionLevel#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#1)]
     [!code-vb[C_ProtectionLevel#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#1)]  
  
### <a name="to-sign-all-message-parts-for-an-operation"></a><span data-ttu-id="ce912-111">Para firmar todas las partes del mensaje para una operación</span><span class="sxs-lookup"><span data-stu-id="ce912-111">To sign all message parts for an operation</span></span>  
  
1. <span data-ttu-id="ce912-112">Cree una interfaz para el servicio y aplique el atributo <xref:System.ServiceModel.ServiceContractAttribute> a la interfaz.</span><span class="sxs-lookup"><span data-stu-id="ce912-112">Create an interface for the service and apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the interface.</span></span>  
  
2. <span data-ttu-id="ce912-113">Agregue una declaración de método a la interfaz.</span><span class="sxs-lookup"><span data-stu-id="ce912-113">Add a method declaration to the interface.</span></span>  
  
3. <span data-ttu-id="ce912-114">Aplique el atributo <xref:System.ServiceModel.OperationContractAttribute> al método, y establezca la propiedad <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> en <xref:System.Net.Security.ProtectionLevel.Sign>, como se muestra en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="ce912-114">Apply the <xref:System.ServiceModel.OperationContractAttribute> attribute to the method, and set the <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> property to <xref:System.Net.Security.ProtectionLevel.Sign>, as shown in the following code.</span></span>  
  
     [!code-csharp[C_ProtectionLevel#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#2)]
     [!code-vb[C_ProtectionLevel#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#2)]  
  
## <a name="protecting-fault-messages"></a><span data-ttu-id="ce912-115">Protección de mensajes de error</span><span class="sxs-lookup"><span data-stu-id="ce912-115">Protecting Fault Messages</span></span>  

 <span data-ttu-id="ce912-116">Las excepciones que se producen en un servicio se pueden enviar a un cliente como errores de SOAP.</span><span class="sxs-lookup"><span data-stu-id="ce912-116">Exceptions that are thrown on a service can be sent to a client as SOAP faults.</span></span> <span data-ttu-id="ce912-117">Para obtener más información sobre cómo crear errores fuertemente tipados, vea [especificar y controlar errores en contratos y servicios](specifying-and-handling-faults-in-contracts-and-services.md) y [Cómo: declarar errores en contratos de servicio](how-to-declare-faults-in-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="ce912-117">For more information about creating strongly typed faults, see [Specifying and Handling Faults in Contracts and Services](specifying-and-handling-faults-in-contracts-and-services.md) and [How to: Declare Faults in Service Contracts](how-to-declare-faults-in-service-contracts.md).</span></span>  
  
#### <a name="to-protect-a-fault-message"></a><span data-ttu-id="ce912-118">Para proteger un mensaje de error</span><span class="sxs-lookup"><span data-stu-id="ce912-118">To protect a fault message</span></span>  
  
1. <span data-ttu-id="ce912-119">Cree un tipo que represente el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="ce912-119">Create a type that represents the fault message.</span></span> <span data-ttu-id="ce912-120">El ejemplo siguiente crea una clase denominada `MathFault` con dos campos.</span><span class="sxs-lookup"><span data-stu-id="ce912-120">The following example creates a class named `MathFault` with two fields.</span></span>  
  
2. <span data-ttu-id="ce912-121">Aplique el atributo <xref:System.Runtime.Serialization.DataContractAttribute> al tipo y un atributo <xref:System.Runtime.Serialization.DataMemberAttribute> a cada campo que se debería serializar, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="ce912-121">Apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the type and a <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to each field that should be serialized, as shown in the following code.</span></span>  
  
     [!code-csharp[C_ProtectionLevel#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#3)]
     [!code-vb[C_ProtectionLevel#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#3)]  
  
3. <span data-ttu-id="ce912-122">En la interfaz que devolverá el error, aplique el atributo <xref:System.ServiceModel.FaultContractAttribute> al método que devolverá el error y establezca el parámetro `detailType` en el tipo de la clase de error.</span><span class="sxs-lookup"><span data-stu-id="ce912-122">In the interface that will return the fault, apply the <xref:System.ServiceModel.FaultContractAttribute> attribute to the method that will return the fault and set the `detailType` parameter to the type of the fault class.</span></span>  
  
4. <span data-ttu-id="ce912-123">También en el constructor, establezca la propiedad <xref:System.ServiceModel.FaultContractAttribute.ProtectionLevel%2A> en <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="ce912-123">Also in the constructor, set the <xref:System.ServiceModel.FaultContractAttribute.ProtectionLevel%2A> property to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>, as shown in the following code.</span></span>  
  
     [!code-csharp[C_ProtectionLevel#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#4)]
     [!code-vb[C_ProtectionLevel#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#4)]  
  
## <a name="protecting-message-parts"></a><span data-ttu-id="ce912-124">Protección de las partes del mensaje</span><span class="sxs-lookup"><span data-stu-id="ce912-124">Protecting Message Parts</span></span>  

 <span data-ttu-id="ce912-125">Use un contrato de mensaje para proteger partes de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="ce912-125">Use a message contract to protect parts of a message.</span></span> <span data-ttu-id="ce912-126">Para obtener más información sobre los contratos de mensajes, vea [usar contratos de mensaje](./feature-details/using-message-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="ce912-126">For more information about message contracts, see [Using Message Contracts](./feature-details/using-message-contracts.md).</span></span>  
  
#### <a name="to-protect-a-message-body"></a><span data-ttu-id="ce912-127">Para proteger el cuerpo de un mensaje</span><span class="sxs-lookup"><span data-stu-id="ce912-127">To protect a message body</span></span>  
  
1. <span data-ttu-id="ce912-128">Cree un tipo que representa al mensaje.</span><span class="sxs-lookup"><span data-stu-id="ce912-128">Create a type that represents the message.</span></span> <span data-ttu-id="ce912-129">El siguiente ejemplo crea una clase `Company` con dos campos, `CompanyName` y `CompanyID`.</span><span class="sxs-lookup"><span data-stu-id="ce912-129">The following example creates a `Company` class with two fields, `CompanyName` and `CompanyID`.</span></span>  
  
2. <span data-ttu-id="ce912-130">Aplique el atributo <xref:System.ServiceModel.MessageContractAttribute> a la clase y establezca la propiedad <xref:System.ServiceModel.MessageContractAttribute.ProtectionLevel%2A> en <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span><span class="sxs-lookup"><span data-stu-id="ce912-130">Apply the <xref:System.ServiceModel.MessageContractAttribute> attribute to the class and set the <xref:System.ServiceModel.MessageContractAttribute.ProtectionLevel%2A> property to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span></span>  
  
3. <span data-ttu-id="ce912-131">Aplique el atributo <xref:System.ServiceModel.MessageHeaderAttribute> a un campo que se expresará como un encabezado de mensaje y establezca la propiedad `ProtectionLevel` en <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span><span class="sxs-lookup"><span data-stu-id="ce912-131">Apply the <xref:System.ServiceModel.MessageHeaderAttribute> attribute to a field that will be expressed as a message header and set the `ProtectionLevel` property to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span></span>  
  
4. <span data-ttu-id="ce912-132">Aplique <xref:System.ServiceModel.MessageBodyMemberAttribute> a cualquier campo que se expresará como parte del cuerpo del mensaje y establezca la `ProtectionLevel` propiedad en <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> , como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ce912-132">Apply the <xref:System.ServiceModel.MessageBodyMemberAttribute> to any field that will be expressed as part of the message body, and set the `ProtectionLevel` property to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>, as shown in the following example.</span></span>  
  
     [!code-csharp[C_ProtectionLevel#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#5)]
     [!code-vb[C_ProtectionLevel#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="ce912-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ce912-133">Example</span></span>  

 <span data-ttu-id="ce912-134">El ejemplo siguiente establece la propiedad `ProtectionLevel` de varias clases de atributos en varios lugares de un servicio.</span><span class="sxs-lookup"><span data-stu-id="ce912-134">The following example sets the `ProtectionLevel` property of several attribute classes at various places in a service.</span></span>  
  
 [!code-csharp[C_ProtectionLevel#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#6)]
 [!code-vb[C_ProtectionLevel#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#6)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ce912-135">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="ce912-135">Compiling the Code</span></span>  

 <span data-ttu-id="ce912-136">En el ejemplo de código siguiente se muestran los espacios de nombres requeridos para compilar el código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ce912-136">The following code shows the namespaces required to compile the example code.</span></span>  
  
 [!code-csharp[C_ProtectionLevel#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#0)]
 [!code-vb[C_ProtectionLevel#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="ce912-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce912-137">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- <xref:System.ServiceModel.FaultContractAttribute>
- <xref:System.ServiceModel.MessageContractAttribute>
- <xref:System.ServiceModel.MessageBodyMemberAttribute>
- [<span data-ttu-id="ce912-138">Descripción de los niveles de protección</span><span class="sxs-lookup"><span data-stu-id="ce912-138">Understanding Protection Level</span></span>](understanding-protection-level.md)
