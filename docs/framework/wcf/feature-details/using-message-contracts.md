---
title: Usar contratos de mensaje
description: Obtenga información sobre cómo usar los atributos de contrato de mensaje para crear un contrato de mensaje que especifique la estructura de un mensaje SOAP en WFC.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message contracts [WCF]
ms.assetid: 1e19c64a-ae84-4c2f-9155-91c54a77c249
ms.openlocfilehash: 39838ac219f095b727ad953158d54da2682a09fa
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96282020"
---
# <a name="using-message-contracts"></a><span data-ttu-id="f9671-103">Usar contratos de mensaje</span><span class="sxs-lookup"><span data-stu-id="f9671-103">Using Message Contracts</span></span>

<span data-ttu-id="f9671-104">Normalmente, al compilar aplicaciones de Windows Communication Foundation (WCF), los desarrolladores prestan mucha atención a las estructuras de datos y a los problemas de serialización y no tienen que preocuparse de la estructura de los mensajes en los que se transportan los datos.</span><span class="sxs-lookup"><span data-stu-id="f9671-104">Typically when building Windows Communication Foundation (WCF) applications, developers pay close attention to the data structures and serialization issues and do not need to concern themselves with the structure of the messages in which the data is carried.</span></span> <span data-ttu-id="f9671-105">Para estas aplicaciones, la creación de contratos de datos para los parámetros o valores devueltos es fácil.</span><span class="sxs-lookup"><span data-stu-id="f9671-105">For these applications, creating data contracts for the parameters or return values is straightforward.</span></span> <span data-ttu-id="f9671-106">(Para obtener más información, consulte [especificar transferencia de datos en contratos de servicio](specifying-data-transfer-in-service-contracts.md)).</span><span class="sxs-lookup"><span data-stu-id="f9671-106">(For more information, see [Specifying Data Transfer in Service Contracts](specifying-data-transfer-in-service-contracts.md).)</span></span>  
  
 <span data-ttu-id="f9671-107">Sin embargo, a veces el control completo sobre la estructura de un mensaje SOAP es tan importante como el control sobre su contenido.</span><span class="sxs-lookup"><span data-stu-id="f9671-107">However, sometimes complete control over the structure of a SOAP message is just as important as control over its contents.</span></span> <span data-ttu-id="f9671-108">Esto es especialmente cierto cuando la interoperabilidad es importante o para controlar específicamente problemas de seguridad del mensaje o parte del mensaje.</span><span class="sxs-lookup"><span data-stu-id="f9671-108">This is especially true when interoperability is important or to specifically control security issues at the level of the message or message part.</span></span> <span data-ttu-id="f9671-109">En estos casos, puede crear un *contrato de mensaje* que le permita especificar la estructura del mensaje SOAP preciso.</span><span class="sxs-lookup"><span data-stu-id="f9671-109">In these cases, you can create a *message contract* that enables you to specify the structure of the precise SOAP message required.</span></span>  
  
 <span data-ttu-id="f9671-110">En este tema, se analiza la forma de usar los diversos atributos de contrato de mensaje para crear un contrato de mensaje específico para su operación.</span><span class="sxs-lookup"><span data-stu-id="f9671-110">This topic discusses how to use the various message contract attributes to create a specific message contract for your operation.</span></span>  
  
## <a name="using-message-contracts-in-operations"></a><span data-ttu-id="f9671-111">Uso de contratos de mensaje en operaciones</span><span class="sxs-lookup"><span data-stu-id="f9671-111">Using Message Contracts in Operations</span></span>  

 <span data-ttu-id="f9671-112">WCF admite operaciones modeladas en el *estilo de llamada a procedimiento remoto (RPC)* o en el *estilo de mensajería*.</span><span class="sxs-lookup"><span data-stu-id="f9671-112">WCF supports operations modeled on either the *remote procedure call (RPC) style* or the *messaging style*.</span></span> <span data-ttu-id="f9671-113">En una operación de estilo de RPC, puede usar cualquier tipo serializable y tiene acceso a las características que están disponibles para las llamadas locales, como múltiples parámetros y `ref` y parámetros `out`.</span><span class="sxs-lookup"><span data-stu-id="f9671-113">In an RPC-style operation, you can use any serializable type, and you have access to the features that are available to local calls, such as multiple parameters and `ref` and `out` parameters.</span></span> <span data-ttu-id="f9671-114">En este estilo, la forma de serialización elegida controla la estructura de los datos en los mensajes subyacentes y el tiempo de ejecución de WCF crea los mensajes para admitir la operación.</span><span class="sxs-lookup"><span data-stu-id="f9671-114">In this style, the form of serialization chosen controls the structure of the data in the underlying messages, and the WCF runtime creates the messages to support the operation.</span></span> <span data-ttu-id="f9671-115">Esto habilita a los desarrolladores que no están familiarizados con SOAP y los mensajes SOAP a crear y utilizar aplicaciones de servicio de manera rápida y sencilla.</span><span class="sxs-lookup"><span data-stu-id="f9671-115">This enables developers who are not familiar with SOAP and SOAP messages to quickly and easily create and use service applications.</span></span>  
  
 <span data-ttu-id="f9671-116">El siguiente código de ejemplo muestra una operación de servicio modelada en el estilo RPC.</span><span class="sxs-lookup"><span data-stu-id="f9671-116">The following code example shows a service operation modeled on the RPC style.</span></span>  
  
```csharp  
[OperationContract]  
public BankingTransactionResponse PostBankingTransaction(BankingTransaction bt);  
```  
  
 <span data-ttu-id="f9671-117">Normalmente, un contrato de datos es suficiente para definir el esquema de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="f9671-117">Normally, a data contract is sufficient to define the schema for the messages.</span></span> <span data-ttu-id="f9671-118">Por ejemplo, en el ejemplo anterior, es suficiente para la mayoría de las aplicaciones si `BankingTransaction` y `BankingTransactionResponse` tienen contratos de datos para definir el contenido de los mensajes SOAP subyacentes.</span><span class="sxs-lookup"><span data-stu-id="f9671-118">For instance, in the preceding example, it is sufficient for most applications if `BankingTransaction` and `BankingTransactionResponse` have data contracts to define the contents of the underlying SOAP messages.</span></span> <span data-ttu-id="f9671-119">Para obtener más información sobre los contratos de datos, consulte [uso de contratos de datos](using-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="f9671-119">For more information about data contracts, see [Using Data Contracts](using-data-contracts.md).</span></span>  
  
 <span data-ttu-id="f9671-120">Sin embargo, de vez en cuando es necesario controlar de manera precisa cómo la estructura del mensaje SOAP se transmite a través de la conexión.</span><span class="sxs-lookup"><span data-stu-id="f9671-120">However, occasionally it is necessary to precisely control how the structure of the SOAP message transmitted over the wire.</span></span> <span data-ttu-id="f9671-121">El escenario más común para esto es insertar encabezados SOAP personalizados.</span><span class="sxs-lookup"><span data-stu-id="f9671-121">The most common scenario for this is inserting custom SOAP headers.</span></span> <span data-ttu-id="f9671-122">Otro escenario común es definir propiedades de seguridad para los encabezados y cuerpo del mensaje, es decir, decidir si estos elementos están firmados y cifrados digitalmente.</span><span class="sxs-lookup"><span data-stu-id="f9671-122">Another common scenario is to define security properties for the message's headers and body, that is, to decide whether these elements are digitally signed and encrypted.</span></span> <span data-ttu-id="f9671-123">Finalmente, algunas pilas de terceros de SOAP necesitan que los mensajes estén en un formato concreto.</span><span class="sxs-lookup"><span data-stu-id="f9671-123">Finally, some third-party SOAP stacks require messages be in a specific format.</span></span> <span data-ttu-id="f9671-124">Las operaciones del estilo de mensajería proporcionan este control.</span><span class="sxs-lookup"><span data-stu-id="f9671-124">Messaging-style operations provide this control.</span></span>  
  
 <span data-ttu-id="f9671-125">Una operación de estilo de mensajería tiene a lo sumo un parámetro y un valor devuelto donde ambos tipos son tipos de mensaje; es decir, serializan directamente en una estructura de mensaje SOAP especificada.</span><span class="sxs-lookup"><span data-stu-id="f9671-125">A messaging-style operation has at most one parameter and one return value where both types are message types; that is, they serialize directly into a specified SOAP message structure.</span></span> <span data-ttu-id="f9671-126">Éste puede ser cualquier tipo marcado con <xref:System.ServiceModel.MessageContractAttribute> o el tipo <xref:System.ServiceModel.Channels.Message>.</span><span class="sxs-lookup"><span data-stu-id="f9671-126">This may be any type marked with the <xref:System.ServiceModel.MessageContractAttribute> or the <xref:System.ServiceModel.Channels.Message> type.</span></span> <span data-ttu-id="f9671-127">El siguiente ejemplo de código muestra una operación similar al estilo RCP anterior, pero que utiliza el estilo de mensajería.</span><span class="sxs-lookup"><span data-stu-id="f9671-127">The following code example shows an operation similar to the preceding RCP-style, but which uses the messaging style.</span></span>  
  
 <span data-ttu-id="f9671-128">Por ejemplo, si `BankingTransaction` y `BankingTransactionResponse` son ambos tipos que son contratos de mensaje, entonces, el código de las siguientes operaciones es válido.</span><span class="sxs-lookup"><span data-stu-id="f9671-128">For example, if `BankingTransaction` and `BankingTransactionResponse` are both types that are message contracts, then the code in the following operations is valid.</span></span>  
  
```csharp  
[OperationContract]  
BankingTransactionResponse Process(BankingTransaction bt);  
[OperationContract]  
void Store(BankingTransaction bt);  
[OperationContract]  
BankingTransactionResponse GetResponse();  
```  
  
 <span data-ttu-id="f9671-129">Sin embargo, el siguiente código no es válido:</span><span class="sxs-lookup"><span data-stu-id="f9671-129">However, the following code is invalid.</span></span>  
  
```csharp  
[OperationContract]  
bool Validate(BankingTransaction bt);  
// Invalid, the return type is not a message contract.  
[OperationContract]  
void Reconcile(BankingTransaction bt1, BankingTransaction bt2);  
// Invalid, there is more than one parameter.  
```  
  
 <span data-ttu-id="f9671-130">Una excepción se produce para cualquier operación que implique un tipo de contrato de mensaje y que no siga uno de los patrones válidos.</span><span class="sxs-lookup"><span data-stu-id="f9671-130">An exception is thrown for any operation that involves a message contract type and that does not follow one of the valid patterns.</span></span> <span data-ttu-id="f9671-131">Por supuesto, las operaciones que no implican tipos de contrato de mensaje no están sujetas a estas restricciones.</span><span class="sxs-lookup"><span data-stu-id="f9671-131">Of course, operations that do not involve message contract types are not subject to these restrictions.</span></span>  
  
 <span data-ttu-id="f9671-132">Si un tipo tiene un contrato de mensaje y un contrato de datos, solo su contrato de mensaje se tiene en cuenta cuando se utiliza el tipo en una operación.</span><span class="sxs-lookup"><span data-stu-id="f9671-132">If a type has both a message contract and a data contract, only its message contract is considered when the type is used in an operation.</span></span>  
  
## <a name="defining-message-contracts"></a><span data-ttu-id="f9671-133">Definición de contratos de mensaje</span><span class="sxs-lookup"><span data-stu-id="f9671-133">Defining Message Contracts</span></span>  

 <span data-ttu-id="f9671-134">Para definir un contrato de mensaje para un tipo (es decir, definir la asignación entre el tipo y una envoltura SOAP), aplique <xref:System.ServiceModel.MessageContractAttribute> al tipo.</span><span class="sxs-lookup"><span data-stu-id="f9671-134">To define a message contract for a type (that is, to define the mapping between the type and a SOAP envelope), apply the <xref:System.ServiceModel.MessageContractAttribute> to the type.</span></span> <span data-ttu-id="f9671-135">A continuación, aplique <xref:System.ServiceModel.MessageHeaderAttribute> a esos miembros del tipo que desea convertir en encabezados SOAP y aplique <xref:System.ServiceModel.MessageBodyMemberAttribute> a esos miembros que desea convertir en partes del cuerpo de SOAP del mensaje.</span><span class="sxs-lookup"><span data-stu-id="f9671-135">Then apply the <xref:System.ServiceModel.MessageHeaderAttribute> to those members of the type you want to make into SOAP headers, and apply the <xref:System.ServiceModel.MessageBodyMemberAttribute> to those members you want to make into parts of the SOAP body of the message.</span></span>  
  
 <span data-ttu-id="f9671-136">El siguiente código proporcionan un ejemplo de uso de un contrato de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f9671-136">The following code provides an example of using a message contract.</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageHeader] public DateTime transactionDate;  
  [MessageBodyMember] private Account sourceAccount;  
  [MessageBodyMember] private Account targetAccount;  
  [MessageBodyMember] public int amount;  
}  
```  
  
 <span data-ttu-id="f9671-137">Cuando se usa este tipo como parámetro de operación, se genera el siguiente sobre SOAP:</span><span class="sxs-lookup"><span data-stu-id="f9671-137">When using this type as an operation parameter, the following SOAP envelope is generated:</span></span>  
  
```xml  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
  <s:Header>  
    <h:operation xmlns:h="http://tempuri.org/" xmlns="http://tempuri.org/">Deposit</h:operation>  
    <h:transactionDate xmlns:h="http://tempuri.org/" xmlns="http://tempuri.org/">2012-02-16T16:10:00</h:transactionDate>  
  </s:Header>  
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <BankingTransaction xmlns="http://tempuri.org/">  
      <amount>0</amount>  
      <sourceAccount xsi:nil="true"/>  
      <targetAccount xsi:nil="true"/>  
    </BankingTransaction>  
  </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="f9671-138">Observe que `operation` y `transactionDate` aparecen como encabezados de SOAP y el cuerpo de SOAP está compuesto por un elemento contenedor `BankingTransaction` que contiene `sourceAccount`,`targetAccount` y `amount`.</span><span class="sxs-lookup"><span data-stu-id="f9671-138">Notice that `operation` and `transactionDate` appear as SOAP headers and the SOAP body consists of a wrapper element `BankingTransaction` containing `sourceAccount`,`targetAccount`, and `amount`.</span></span>  
  
 <span data-ttu-id="f9671-139">Puede aplicar <xref:System.ServiceModel.MessageHeaderAttribute> y <xref:System.ServiceModel.MessageBodyMemberAttribute> a todos los campos, propiedades y eventos, sin tener en cuenta si son públicos, privados, protegidos o internos.</span><span class="sxs-lookup"><span data-stu-id="f9671-139">You can apply the <xref:System.ServiceModel.MessageHeaderAttribute> and <xref:System.ServiceModel.MessageBodyMemberAttribute> to all fields, properties, and events, regardless of whether they are public, private, protected, or internal.</span></span>  
  
 <span data-ttu-id="f9671-140"><xref:System.ServiceModel.MessageContractAttribute> permite especificar los atributos WrapperName y WrapperNamespace que controlan el nombre del elemento contenedor en el cuerpo del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="f9671-140">The <xref:System.ServiceModel.MessageContractAttribute> allows you to specify the WrapperName and WrapperNamespace attributes which control the name of the wrapper element in the body of the SOAP message.</span></span> <span data-ttu-id="f9671-141">De forma predeterminada el nombre del tipo de contrato de mensaje se usa para el contenedor y el espacio de nombres en el que se define el contrato de mensaje; `http://tempuri.org/` se usa como espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f9671-141">By default the name of the message contract type is used for the wrapper and the namespace in which the message contract is defined `http://tempuri.org/` is used as the default namespace.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f9671-142">Los atributos <xref:System.Runtime.Serialization.KnownTypeAttribute> se omiten en los contratos de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f9671-142"><xref:System.Runtime.Serialization.KnownTypeAttribute> attributes are ignored in message contracts.</span></span> <span data-ttu-id="f9671-143">Si se requiere un <xref:System.Runtime.Serialization.KnownTypeAttribute>, colóquelo en la operación que esté utilizando el contrato de mensaje en cuestión.</span><span class="sxs-lookup"><span data-stu-id="f9671-143">If a <xref:System.Runtime.Serialization.KnownTypeAttribute> is required, place it on the operation that is using the message contract in question.</span></span>  
  
## <a name="controlling-header-and-body-part-names-and-namespaces"></a><span data-ttu-id="f9671-144">Controlar los nombres y espacios de nombres del encabezado y parte del cuerpo</span><span class="sxs-lookup"><span data-stu-id="f9671-144">Controlling Header and Body Part Names and Namespaces</span></span>  

 <span data-ttu-id="f9671-145">En la representación de SOAP de un contrato de mensaje, cada encabezado y la parte del cuerpo se asigna a un elemento XML que tiene un nombre y un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="f9671-145">In the SOAP representation of a message contract, each header and body part maps to an XML element that has a name and a namespace.</span></span>  
  
 <span data-ttu-id="f9671-146">De forma predeterminada, el espacio de nombres es igual que el espacio de nombres del contrato de servicio en el que el participa el mensaje y el nombre está determinado por el nombre de miembro al que se aplican los atributos <xref:System.ServiceModel.MessageHeaderAttribute> o <xref:System.ServiceModel.MessageBodyMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f9671-146">By default, the namespace is the same as the namespace of the service contract that the message is participating in, and the name is determined by the member name to which the <xref:System.ServiceModel.MessageHeaderAttribute> or the <xref:System.ServiceModel.MessageBodyMemberAttribute> attributes are applied.</span></span>  
  
 <span data-ttu-id="f9671-147">Puede cambiar estos valores predeterminados manipulando las propiedades <xref:System.ServiceModel.MessageContractMemberAttribute.Name%2A?displayProperty=nameWithType> y <xref:System.ServiceModel.MessageContractMemberAttribute.Namespace%2A?displayProperty=nameWithType> (en la clase primaria de los atributos de las clases <xref:System.ServiceModel.MessageHeaderAttribute> y <xref:System.ServiceModel.MessageBodyMemberAttribute>).</span><span class="sxs-lookup"><span data-stu-id="f9671-147">You can change these defaults by manipulating the <xref:System.ServiceModel.MessageContractMemberAttribute.Name%2A?displayProperty=nameWithType> and <xref:System.ServiceModel.MessageContractMemberAttribute.Namespace%2A?displayProperty=nameWithType> (on the parent class of the <xref:System.ServiceModel.MessageHeaderAttribute> and <xref:System.ServiceModel.MessageBodyMemberAttribute> attributes).</span></span>  
  
 <span data-ttu-id="f9671-148">Considere la clase del siguiente ejemplo de código:</span><span class="sxs-lookup"><span data-stu-id="f9671-148">Consider the class in the following code example.</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageHeader(Namespace="http://schemas.contoso.com/auditing/2005")] public bool IsAudited;  
  [MessageBodyMember(Name="transactionData")] public BankingTransactionData theData;  
}  
```  
  
 <span data-ttu-id="f9671-149">En este ejemplo, el encabezado `IsAudited` está en el espacio de nombres especificado en el código y un elemento XML representa la parte del cuerpo que representa el miembro `theData` con el nombre `transactionData`.</span><span class="sxs-lookup"><span data-stu-id="f9671-149">In this example, the `IsAudited` header is in the namespace specified in the code, and the body part that represents the `theData` member is represented by an XML element with the name `transactionData`.</span></span> <span data-ttu-id="f9671-150">A continuación se muestra el XML generado para este contrato de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f9671-150">The following shows the XML generated for this message contract.</span></span>  
  
```xml  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
  <s:Header>  
    <h:IsAudited xmlns:h="http://schemas.contoso.com/auditing/2005" xmlns="http://schemas.contoso.com/auditing/2005">false</h:IsAudited>  
    <h:operation xmlns:h="http://tempuri.org/" xmlns="http://tempuri.org/">Deposit</h:operation>  
  </s:Header>  
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <AuditedBankingTransaction xmlns="http://tempuri.org/">  
      <transactionData/>  
    </AuditedBankingTransaction>  
  </s:Body>  
</s:Envelope>  
```  
  
## <a name="controlling-whether-the-soap-body-parts-are-wrapped"></a><span data-ttu-id="f9671-151">Controlar si las partes de cuerpo de SOAP están ajustadas</span><span class="sxs-lookup"><span data-stu-id="f9671-151">Controlling Whether the SOAP Body Parts Are Wrapped</span></span>  

 <span data-ttu-id="f9671-152">De forma predeterminada, las partes de cuerpo de SOAP se serializan dentro de un elemento ajustado.</span><span class="sxs-lookup"><span data-stu-id="f9671-152">By default, the SOAP body parts are serialized inside a wrapped element.</span></span> <span data-ttu-id="f9671-153">Por ejemplo, el siguiente código muestra el elemento contenedor `HelloGreetingMessage` generado a partir del nombre del tipo <xref:System.ServiceModel.MessageContractAttribute> en el contrato del mensaje para el mensaje `HelloGreetingMessage`.</span><span class="sxs-lookup"><span data-stu-id="f9671-153">For example, the following code shows the `HelloGreetingMessage` wrapper element generated from the name of the <xref:System.ServiceModel.MessageContractAttribute> type in the message contract for the `HelloGreetingMessage` message.</span></span>  
  
[!code-csharp[MessageHeaderAttribute#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/messageheaderattribute/cs/services.cs#3)]
[!code-vb[MessageHeaderAttribute#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/messageheaderattribute/vb/services.vb#3)]  
  
 <span data-ttu-id="f9671-154">Para suprimir el elemento contenedor, establezca la propiedad <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="f9671-154">To suppress the wrapper element, set the <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> property to `false`.</span></span> <span data-ttu-id="f9671-155">Para controlar el nombre y el espacio de nombres del elemento contenedor, use las propiedades <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A> y <xref:System.ServiceModel.MessageContractAttribute.WrapperNamespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="f9671-155">To control the name and the namespace of the wrapper element, use the <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A> and <xref:System.ServiceModel.MessageContractAttribute.WrapperNamespace%2A> properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f9671-156">Tener más de una parte de cuerpo de mensaje en mensajes que no se ajustan no es conforme a WS-I Basic Profile 1.1 y no se recomienda al diseñar nuevos contratos de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f9671-156">Having more than one message body part in messages that are not wrapped is not compliant with WS-I Basic Profile 1.1 and is not recommended when designing new message contracts.</span></span> <span data-ttu-id="f9671-157">Sin embargo, puede ser necesario para tener más de una parte del cuerpo de mensaje sin ajustar en ciertos escenarios de interoperabilidad concretos.</span><span class="sxs-lookup"><span data-stu-id="f9671-157">However, it may be necessary to have more than one unwrapped message body part in certain specific interoperability scenarios.</span></span> <span data-ttu-id="f9671-158">Si va a transmitir más de una parte de datos en un cuerpo del mensaje, se recomienda que use el modo predeterminado (ajustado).</span><span class="sxs-lookup"><span data-stu-id="f9671-158">If you are going to transmit more than one piece of data in a message body, it is recommended to use the default (wrapped) mode.</span></span> <span data-ttu-id="f9671-159">Tener más de un encabezado de mensaje en mensajes sin ajustar es completamente aceptable.</span><span class="sxs-lookup"><span data-stu-id="f9671-159">Having more than one message header in unwrapped messages is completely acceptable.</span></span>  
  
## <a name="using-custom-types-inside-message-contracts"></a><span data-ttu-id="f9671-160">Uso de tipos personalizados dentro de contratos de mensaje</span><span class="sxs-lookup"><span data-stu-id="f9671-160">Using Custom Types Inside Message Contracts</span></span>  

 <span data-ttu-id="f9671-161">Cada encabezado de mensaje individual y parte del cuerpo del mensaje se serializa (se convierte en XML) utilizando el motor de serialización elegido para el contrato de servicio donde se use el mensaje.</span><span class="sxs-lookup"><span data-stu-id="f9671-161">Each individual message header and message body part is serialized (turned into XML) using the chosen serialization engine for the service contract where the message is used.</span></span> <span data-ttu-id="f9671-162">El motor de serialización predeterminado, `XmlFormatter`, puede manejar cualquier tipo que tenga un contrato de datos, explícitamente (teniendo <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=nameWithType>) o implícitamente (siendo un tipo primitivo, teniendo <xref:System.SerializableAttribute?displayProperty=nameWithType>, etc.).</span><span class="sxs-lookup"><span data-stu-id="f9671-162">The default serialization engine, the `XmlFormatter`, can handle any type that has a data contract, either explicitly (by having the <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=nameWithType>) or implicitly (by being a primitive type, having the <xref:System.SerializableAttribute?displayProperty=nameWithType>, and so on).</span></span> <span data-ttu-id="f9671-163">Para obtener más información, consulte [uso de contratos de datos](using-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="f9671-163">For more information, see [Using Data Contracts](using-data-contracts.md).</span></span>  
  
 <span data-ttu-id="f9671-164">En el ejemplo anterior, `Operation` y los tipos `BankingTransactionData` deben tener un contrato de datos y `transactionDate` es serializable porque <xref:System.DateTime> es un primitivo (y, por ende, tiene un contrato de datos implícito).</span><span class="sxs-lookup"><span data-stu-id="f9671-164">In the preceding example, the `Operation` and `BankingTransactionData` types must have a data contract, and `transactionDate` is serializable because <xref:System.DateTime> is a primitive (and so has an implicit data contract).</span></span>  
  
 <span data-ttu-id="f9671-165">Sin embargo, es posible cambiar a un motor de serialización diferente, `XmlSerializer`.</span><span class="sxs-lookup"><span data-stu-id="f9671-165">However, it is possible to switch to a different serialization engine, the `XmlSerializer`.</span></span> <span data-ttu-id="f9671-166">Si realiza este cambio, debería asegurarse de que todos los tipos utilizados para los encabezados del mensaje y partes del cuerpo son serializables utilizando `XmlSerializer`.</span><span class="sxs-lookup"><span data-stu-id="f9671-166">If you make such a switch, you should ensure that all of the types used for message headers and body parts are serializable using the `XmlSerializer`.</span></span>  
  
## <a name="using-arrays-inside-message-contracts"></a><span data-ttu-id="f9671-167">Uso de matrices dentro de los contratos de mensaje</span><span class="sxs-lookup"><span data-stu-id="f9671-167">Using Arrays Inside Message Contracts</span></span>  

 <span data-ttu-id="f9671-168">Puede utilizar matrices de elementos repetitivos en contratos de mensaje de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="f9671-168">You can use arrays of repeating elements in message contracts in two ways.</span></span>  
  
 <span data-ttu-id="f9671-169">La primera consiste en utilizar <xref:System.ServiceModel.MessageHeaderAttribute> o <xref:System.ServiceModel.MessageBodyMemberAttribute> directamente en la matriz.</span><span class="sxs-lookup"><span data-stu-id="f9671-169">The first is to use a <xref:System.ServiceModel.MessageHeaderAttribute> or a <xref:System.ServiceModel.MessageBodyMemberAttribute> directly on the array.</span></span> <span data-ttu-id="f9671-170">En este caso, toda la matriz se serializa como un elemento (es decir, un encabezado o una parte del cuerpo) con múltiples elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="f9671-170">In this case, the entire array is serialized as one element (that is, one header or one body part) with multiple child elements.</span></span> <span data-ttu-id="f9671-171">Considere la clase del siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f9671-171">Consider the class in the following example.</span></span>  
  
```csharp  
[MessageContract]  
public class BankingDepositLog  
{  
  [MessageHeader] public int numRecords;  
  [MessageHeader] public DepositRecord[] records;  
  [MessageHeader] public int branchID;  
}  
```  
  
 <span data-ttu-id="f9671-172">Esto resulta en encabezados SOAP similares a los siguientes.</span><span class="sxs-lookup"><span data-stu-id="f9671-172">This results in SOAP headers is similar to the following.</span></span>  
  
```xml  
<BankingDepositLog>  
<numRecords>3</numRecords>  
<records>  
  <DepositRecord>Record1</DepositRecord>  
  <DepositRecord>Record2</DepositRecord>  
  <DepositRecord>Record3</DepositRecord>  
</records>  
<branchID>20643</branchID>  
</BankingDepositLog>  
```  
  
 <span data-ttu-id="f9671-173">Como alternativa se puede utilizar <xref:System.ServiceModel.MessageHeaderArrayAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f9671-173">An alternative to this is to use the <xref:System.ServiceModel.MessageHeaderArrayAttribute>.</span></span> <span data-ttu-id="f9671-174">En este caso, cada elemento de matriz se serializa independientemente y, por tanto, cada elemento de matriz tiene un encabezado, similar a lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f9671-174">In this case, each array element is serialized independently and so that each array element has one header, similar to the following.</span></span>  
  
```xml  
<numRecords>3</numRecords>  
<records>Record1</records>  
<records>Record2</records>  
<records>Record3</records>  
<branchID>20643</branchID>  
```  
  
 <span data-ttu-id="f9671-175">El nombre predeterminado para las entradas de la matriz es el nombre del miembro al que se aplican los atributos <xref:System.ServiceModel.MessageHeaderArrayAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f9671-175">The default name for array entries is the name of the member to which the <xref:System.ServiceModel.MessageHeaderArrayAttribute> attributes is applied.</span></span>  
  
 <span data-ttu-id="f9671-176">El atributo <xref:System.ServiceModel.MessageHeaderArrayAttribute> hereda de <xref:System.ServiceModel.MessageHeaderAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f9671-176">The <xref:System.ServiceModel.MessageHeaderArrayAttribute> attribute inherits from the <xref:System.ServiceModel.MessageHeaderAttribute>.</span></span> <span data-ttu-id="f9671-177">Tiene el mismo conjunto de características como los atributos que no son de matriz, por ejemplo, es posible establecer el orden, nombre y espacio de nombres de una matriz de encabezados de la misma manera que se establece para un encabezado único.</span><span class="sxs-lookup"><span data-stu-id="f9671-177">It has the same set of features as the non-array attributes, for example, it is possible to set the order, name, and namespace for an array of headers in the same way you set it for a single header.</span></span> <span data-ttu-id="f9671-178">Al utilizar la propiedad `Order` en una matriz, se aplica a toda la matriz.</span><span class="sxs-lookup"><span data-stu-id="f9671-178">When you use the `Order` property on an array, it applies to the entire array.</span></span>  
  
 <span data-ttu-id="f9671-179">Solo puede aplicar <xref:System.ServiceModel.MessageHeaderArrayAttribute> a las matrices, no a las colecciones.</span><span class="sxs-lookup"><span data-stu-id="f9671-179">You can apply the <xref:System.ServiceModel.MessageHeaderArrayAttribute> only to arrays, not collections.</span></span>  
  
## <a name="using-byte-arrays-in-message-contracts"></a><span data-ttu-id="f9671-180">Uso de las matrices de bytes en contratos de mensaje</span><span class="sxs-lookup"><span data-stu-id="f9671-180">Using Byte Arrays in Message Contracts</span></span>  

 <span data-ttu-id="f9671-181">Las matrices de bytes, cuando se usan con los atributos que no son de matriz (<xref:System.ServiceModel.MessageBodyMemberAttribute> y <xref:System.ServiceModel.MessageHeaderAttribute>), no se tratan como matrices, sino como un tipo primitivo especial representado como datos con codificación Base64 en el XML resultante.</span><span class="sxs-lookup"><span data-stu-id="f9671-181">Byte arrays, when used with the non-array attributes (<xref:System.ServiceModel.MessageBodyMemberAttribute> and <xref:System.ServiceModel.MessageHeaderAttribute>), are not treated as arrays but as a special primitive type represented as Base64-encoded data in the resulting XML.</span></span>  
  
 <span data-ttu-id="f9671-182">Al utilizar las matrices de bytes con el atributo de matriz <xref:System.ServiceModel.MessageHeaderArrayAttribute>, los resultados dependen del serializador que se utilice.</span><span class="sxs-lookup"><span data-stu-id="f9671-182">When you use byte arrays with the array attribute <xref:System.ServiceModel.MessageHeaderArrayAttribute>, the results depend on the serializer in use.</span></span> <span data-ttu-id="f9671-183">Con el serializador predeterminado, la matriz se representa como una entrada individual para cada byte.</span><span class="sxs-lookup"><span data-stu-id="f9671-183">With the default serializer, the array is represented as an individual entry for each byte.</span></span> <span data-ttu-id="f9671-184">Sin embargo, cuando se selecciona`XmlSerializer`, (usando <xref:System.ServiceModel.XmlSerializerFormatAttribute> en el contrato de servicio) las matrices de bytes se tratan como datos Base64 independientemente de si se utilizan los atributos que son de matriz o los que no son de matriz.</span><span class="sxs-lookup"><span data-stu-id="f9671-184">However, when the `XmlSerializer` is selected, (using the <xref:System.ServiceModel.XmlSerializerFormatAttribute> on the service contract), byte arrays are treated as Base64 data regardless of whether the array or non-array attributes are used.</span></span>  
  
## <a name="signing-and-encrypting-parts-of-the-message"></a><span data-ttu-id="f9671-185">Firmado y cifrado de partes del mensaje</span><span class="sxs-lookup"><span data-stu-id="f9671-185">Signing and Encrypting Parts of the Message</span></span>  

 <span data-ttu-id="f9671-186">Un contrato de mensaje puede indicar si los encabezados y/o cuerpo del mensaje deberían estar firmados y cifrados digitalmente.</span><span class="sxs-lookup"><span data-stu-id="f9671-186">A message contract can indicate whether the headers and/or body of the message should be digitally signed and encrypted.</span></span>  
  
 <span data-ttu-id="f9671-187">Esto se hace estableciendo la propiedad <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A?displayProperty=nameWithType> en los atributos de las clases <xref:System.ServiceModel.MessageHeaderAttribute> y <xref:System.ServiceModel.MessageBodyMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f9671-187">This is done by setting the <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A?displayProperty=nameWithType> property on the <xref:System.ServiceModel.MessageHeaderAttribute> and <xref:System.ServiceModel.MessageBodyMemberAttribute> attributes.</span></span> <span data-ttu-id="f9671-188">La propiedad es una enumeración del tipo <xref:System.Net.Security.ProtectionLevel?displayProperty=nameWithType> y se puede establecer como <xref:System.Net.Security.ProtectionLevel.None> (sin cifrado ni firma), <xref:System.Net.Security.ProtectionLevel.Sign> (solo firma digital) o <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> (cifrado y firma digital).</span><span class="sxs-lookup"><span data-stu-id="f9671-188">The property is an enumeration of the <xref:System.Net.Security.ProtectionLevel?displayProperty=nameWithType> type and can be set to <xref:System.Net.Security.ProtectionLevel.None> (no encryption or signature), <xref:System.Net.Security.ProtectionLevel.Sign> (digital signature only), or <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> (both encryption and a digital signature).</span></span> <span data-ttu-id="f9671-189">De manera predeterminada, es <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span><span class="sxs-lookup"><span data-stu-id="f9671-189">The default is <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span></span>  
  
 <span data-ttu-id="f9671-190">Para que estas características de seguridad funcionen, debe configurar correctamente el enlace y los comportamientos.</span><span class="sxs-lookup"><span data-stu-id="f9671-190">For these security features to work, you must properly configure the binding and behaviors.</span></span> <span data-ttu-id="f9671-191">Si utiliza estas características de seguridad sin la configuración apropiada (por ejemplo, intentando firmar un mensaje sin proporcionar sus credenciales), una excepción se producirá en el momento de la validación.</span><span class="sxs-lookup"><span data-stu-id="f9671-191">If you use these security features without the proper configuration (for example, attempting to sign a message without supplying your credentials), an exception is thrown at validation time.</span></span>  
  
 <span data-ttu-id="f9671-192">Para los encabezados de mensajes, el nivel de protección se determina individualmente para cada encabezado.</span><span class="sxs-lookup"><span data-stu-id="f9671-192">For message headers, the protection level is determined individually for each header.</span></span>  
  
 <span data-ttu-id="f9671-193">Para las partes del cuerpo del mensaje, el nivel de protección puede verse como el "nivel de protección mínimo".</span><span class="sxs-lookup"><span data-stu-id="f9671-193">For message body parts, the protection level can be thought of as the "minimum protection level."</span></span> <span data-ttu-id="f9671-194">El cuerpo tiene solo un nivel de protección, independientemente del número de partes del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="f9671-194">The body has only one protection level, regardless of the number of body parts.</span></span> <span data-ttu-id="f9671-195">El nivel de protección del cuerpo lo determina el valor de propiedad <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A> más alto de todas las partes del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="f9671-195">The protection level of the body is determined by the highest <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A> property setting of all the body parts.</span></span> <span data-ttu-id="f9671-196">Sin embargo, debería establecer el nivel de protección de cada parte del cuerpo en el nivel de protección mínimo real necesario.</span><span class="sxs-lookup"><span data-stu-id="f9671-196">However, you should set the protection level of each body part to the actual minimum protection level required.</span></span>  
  
 <span data-ttu-id="f9671-197">Considere la clase del siguiente ejemplo de código:</span><span class="sxs-lookup"><span data-stu-id="f9671-197">Consider the class in the following code example.</span></span>  
  
```csharp  
[MessageContract]  
public class PatientRecord  
{  
   [MessageHeader(ProtectionLevel=None)] public int recordID;  
   [MessageHeader(ProtectionLevel=Sign)] public string patientName;  
   [MessageHeader(ProtectionLevel=EncryptAndSign)] public string SSN;  
   [MessageBodyMember(ProtectionLevel=None)] public string comments;  
   [MessageBodyMember(ProtectionLevel=Sign)] public string diagnosis;  
   [MessageBodyMember(ProtectionLevel=EncryptAndSign)] public string medicalHistory;  
}  
```  
  
 <span data-ttu-id="f9671-198">En este ejemplo, el encabezado `recordID` no está protegido, `patientName` está `signed`, y `SSN` está cifrado y firmado.</span><span class="sxs-lookup"><span data-stu-id="f9671-198">In this example, the `recordID` header is not protected, `patientName` is `signed`, and `SSN` is encrypted and signed.</span></span> <span data-ttu-id="f9671-199">Al menos una parte del cuerpo, `medicalHistory`, tiene <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> aplicado y, de este modo, el cuerpo del mensaje completo se cifra y firma, aun cuando las partes del cuerpo de comentarios y diagnóstico especifican niveles de protección inferiores.</span><span class="sxs-lookup"><span data-stu-id="f9671-199">At least one body part, `medicalHistory`, has <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> applied, and thus the entire message body is encrypted and signed, even though the comments and diagnosis body parts specify lower protection levels.</span></span>  
  
## <a name="soap-action"></a><span data-ttu-id="f9671-200">Acción de SOAP</span><span class="sxs-lookup"><span data-stu-id="f9671-200">SOAP Action</span></span>  

 <span data-ttu-id="f9671-201">SOAP y los estándares de los servicios Web relacionados definen una propiedad llamada `Action` que puede estar presente en cada mensaje SOAP enviado.</span><span class="sxs-lookup"><span data-stu-id="f9671-201">SOAP and related Web services standards define a property called `Action` that can be present for every SOAP message sent.</span></span> <span data-ttu-id="f9671-202">Las propiedades <xref:System.ServiceModel.OperationContractAttribute.Action%2A?displayProperty=nameWithType> y <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A?displayProperty=nameWithType> de la operación controlan el valor de esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="f9671-202">The operation's <xref:System.ServiceModel.OperationContractAttribute.Action%2A?displayProperty=nameWithType> and <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A?displayProperty=nameWithType> properties control the value of this property.</span></span>  
  
## <a name="soap-header-attributes"></a><span data-ttu-id="f9671-203">Atributos de encabezado SOAP</span><span class="sxs-lookup"><span data-stu-id="f9671-203">SOAP Header Attributes</span></span>  

 <span data-ttu-id="f9671-204">El estándar de SOAP define los siguientes atributos que pueden existir en un encabezado:</span><span class="sxs-lookup"><span data-stu-id="f9671-204">The SOAP standard defines the following attributes that may exist on a header:</span></span>  
  
- <span data-ttu-id="f9671-205">`Actor/Role` (`Actor` en SOAP 1.1, `Role` en SOAP 1.2)</span><span class="sxs-lookup"><span data-stu-id="f9671-205">`Actor/Role` (`Actor` in SOAP 1.1, `Role` in SOAP 1.2)</span></span>  
  
- `MustUnderstand`  
  
- `Relay`  
  
 <span data-ttu-id="f9671-206">El atributo `Actor` o `Role` especifica el Identificador uniforme de recursos (URI) del nodo para el que está dirigido un encabezado determinado.</span><span class="sxs-lookup"><span data-stu-id="f9671-206">The `Actor` or `Role` attribute specifies the Uniform Resource Identifier (URI) of the node for which a given header is intended.</span></span> <span data-ttu-id="f9671-207">El atributo `MustUnderstand` especifica si el nodo que procesa el encabezado debe entenderlo.</span><span class="sxs-lookup"><span data-stu-id="f9671-207">The `MustUnderstand` attribute specifies whether the node processing the header must understand it.</span></span> <span data-ttu-id="f9671-208">El atributo `Relay` especifica si el encabezado se va a retransmitir a los nodos descendentes.</span><span class="sxs-lookup"><span data-stu-id="f9671-208">The `Relay` attribute specifies whether the header is to be relayed to downstream nodes.</span></span> <span data-ttu-id="f9671-209">WCF no realiza ningún procesamiento de estos atributos en los mensajes entrantes, salvo el `MustUnderstand` atributo, como se especifica en la sección "versiones de contrato de mensaje" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="f9671-209">WCF does not perform any processing of these attributes on incoming messages, except for the `MustUnderstand` attribute, as specified in the "Message Contract Versioning" section later in this topic.</span></span> <span data-ttu-id="f9671-210">Sin embargo, le permite leer y escribir estos atributos según sea necesario, como en la siguiente descripción.</span><span class="sxs-lookup"><span data-stu-id="f9671-210">However, it allows you to read and write these attributes as necessary, as in the following description.</span></span>  
  
 <span data-ttu-id="f9671-211">Al enviar un mensaje, no se emiten estos atributos de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f9671-211">When sending a message, these attributes are not emitted by default.</span></span> <span data-ttu-id="f9671-212">Esto se puede cambiar de dos formas:</span><span class="sxs-lookup"><span data-stu-id="f9671-212">You can change this in two ways.</span></span> <span data-ttu-id="f9671-213">Primero, puede establecer de manera estática los atributos en cualquier valor que desee cambiando las propiedades <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A?displayProperty=nameWithType>, <xref:System.ServiceModel.MessageHeaderAttribute.MustUnderstand%2A?displayProperty=nameWithType> y <xref:System.ServiceModel.MessageHeaderAttribute.Relay%2A?displayProperty=nameWithType>, tal y como se muestra en el siguiente ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="f9671-213">First, you may statically set the attributes to any desired values by changing the <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A?displayProperty=nameWithType>, <xref:System.ServiceModel.MessageHeaderAttribute.MustUnderstand%2A?displayProperty=nameWithType>, and <xref:System.ServiceModel.MessageHeaderAttribute.Relay%2A?displayProperty=nameWithType> properties, as shown in the following code example.</span></span> <span data-ttu-id="f9671-214">(Observe que no hay propiedad `Role`; establecer la propiedad <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A> emite el atributo `Role` si usa SOAP 1.2).</span><span class="sxs-lookup"><span data-stu-id="f9671-214">(Note that there is no `Role` property; setting the <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A> property emits the `Role` attribute if you are using SOAP 1.2).</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader(Actor="http://auditingservice.contoso.com", MustUnderstand=true)] public bool IsAudited;  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public BankingTransactionData theData;  
}  
```  
  
 <span data-ttu-id="f9671-215">La segunda manera de controlar estos atributos es de manera dinámica, mediante código.</span><span class="sxs-lookup"><span data-stu-id="f9671-215">The second way to control these attributes is dynamically, through code.</span></span> <span data-ttu-id="f9671-216">Puede lograr esto ajustando el tipo de encabezado deseado en el tipo <xref:System.ServiceModel.MessageHeader%601> (asegúrese de no confundir este tipo con la versión no genérica) y usando el tipo junto con la clase <xref:System.ServiceModel.MessageHeaderAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f9671-216">You can achieve this by wrapping the desired header type in the <xref:System.ServiceModel.MessageHeader%601> type (be sure not to confuse this type with the non-generic version) and by using the type together with the <xref:System.ServiceModel.MessageHeaderAttribute>.</span></span> <span data-ttu-id="f9671-217">A continuación, puede usar las propiedades de la clase <xref:System.ServiceModel.MessageHeader%601> para establecer los atributos SOAP, tal y como se muestra en el siguiente ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="f9671-217">Then, you can use properties on the <xref:System.ServiceModel.MessageHeader%601> to set the SOAP attributes, as shown in the following code example.</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public MessageHeader<bool> IsAudited;  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public BankingTransactionData theData;  
}  
// application code:  
BankingTransaction bt = new BankingTransaction();  
bt.IsAudited = new MessageHeader<bool>();  
bt.IsAudited.Content = false; // Set IsAudited header value to "false"  
bt.IsAudited.Actor="http://auditingservice.contoso.com";  
bt.IsAudited.MustUnderstand=true;  
```  
  
 <span data-ttu-id="f9671-218">Si utiliza los mecanismos de control dinámico y estático, los ajustes estáticos se utilizan como valores predeterminados, pero pueden invalidarse después mediante el uso del mecanismo dinámico, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f9671-218">If you use both the dynamic and the static control mechanisms, the static settings are used as a default but can later be overridden by using the dynamic mechanism, as shown in the following code.</span></span>  
  
```csharp  
[MessageHeader(MustUnderstand=true)] public MessageHeader<Person> documentApprover;  
// later on in the code:  
BankingTransaction bt = new BankingTransaction();  
bt.documentApprover = new MessageHeader<Person>();  
bt.documentApprover.MustUnderstand = false; // override the static default of 'true'  
```  
  
 <span data-ttu-id="f9671-219">Se permite la creación de encabezados repetidos con control de atributo dinámico, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f9671-219">Creating repeated headers with dynamic attribute control is allowed, as shown in the following code.</span></span>  
  
```csharp  
[MessageHeaderArray] public MessageHeader<Person> documentApprovers[];  
```  
  
 <span data-ttu-id="f9671-220">En el lado receptor, solo se pueden leer estos atributos de SOAP si se utiliza la clase <xref:System.ServiceModel.MessageHeader%601> para el encabezado en el tipo.</span><span class="sxs-lookup"><span data-stu-id="f9671-220">On the receiving side, reading these SOAP attributes can only be done if the <xref:System.ServiceModel.MessageHeader%601> class is used for the header in the type.</span></span> <span data-ttu-id="f9671-221">Examine las propiedades `Actor`, `Relay` o `MustUnderstand` de un encabezado del tipo <xref:System.ServiceModel.MessageHeader%601> para detectar los valores de atributos en el mensaje recibido.</span><span class="sxs-lookup"><span data-stu-id="f9671-221">Examine the `Actor`, `Relay`, or `MustUnderstand` properties of a header of the <xref:System.ServiceModel.MessageHeader%601> type to discover the attribute settings on the received message.</span></span>  
  
 <span data-ttu-id="f9671-222">Cuando se recibe un mensaje y después se devuelve, los valores de atributo de SOAP solo son de ida y vuelta para encabezados de tipo <xref:System.ServiceModel.MessageHeader%601>.</span><span class="sxs-lookup"><span data-stu-id="f9671-222">When a message is received and then sent back, the SOAP attribute settings only go round-trip for headers of the <xref:System.ServiceModel.MessageHeader%601> type.</span></span>  
  
## <a name="order-of-soap-body-parts"></a><span data-ttu-id="f9671-223">Orden de partes de cuerpo de SOAP</span><span class="sxs-lookup"><span data-stu-id="f9671-223">Order of SOAP Body Parts</span></span>  

 <span data-ttu-id="f9671-224">En algunas circunstancias, puede que tenga que controlar el orden de partes del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="f9671-224">In some circumstances, you may need to control the order of the body parts.</span></span> <span data-ttu-id="f9671-225">De forma predeterminada, el orden de los elementos del cuerpo es alfabético, pero puede controlarse mediante la propiedad <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f9671-225">The order of the body elements is alphabetical by default, but can be controlled by the <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="f9671-226">Esta propiedad tiene la misma semántica que la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A?displayProperty=nameWithType>, salvo el comportamiento en escenarios de herencia (en contratos de mensaje, los miembros de cuerpo de tipo base no están ordenados antes de los miembros de cuerpo de tipo derivado).</span><span class="sxs-lookup"><span data-stu-id="f9671-226">This property has the same semantics as the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A?displayProperty=nameWithType> property, except for the behavior in inheritance scenarios (in message contracts, base type body members are not sorted before the derived type body members).</span></span> <span data-ttu-id="f9671-227">Para obtener más información, vea orden de los [miembros de datos](data-member-order.md).</span><span class="sxs-lookup"><span data-stu-id="f9671-227">For more information, see [Data Member Order](data-member-order.md).</span></span>  
  
 <span data-ttu-id="f9671-228">En el siguiente ejemplo, `amount` vendría normalmente primero porque es primero alfabéticamente.</span><span class="sxs-lookup"><span data-stu-id="f9671-228">In the following example, `amount` would normally come first because it is first alphabetically.</span></span> <span data-ttu-id="f9671-229">Sin embargo, la propiedad <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A> lo coloca en la tercera posición.</span><span class="sxs-lookup"><span data-stu-id="f9671-229">However, the <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A> property puts it into the third position.</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember(Order=1)] public Account sourceAccount;  
  [MessageBodyMember(Order=2)] public Account targetAccount;  
  [MessageBodyMember(Order=3)] public int amount;  
}  
```  
  
## <a name="message-contract-versioning"></a><span data-ttu-id="f9671-230">Versiones de contratos de mensaje</span><span class="sxs-lookup"><span data-stu-id="f9671-230">Message Contract Versioning</span></span>  

 <span data-ttu-id="f9671-231">De vez en cuando, puede necesitar cambiar los contratos de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f9671-231">Occasionally, you may need to change message contracts.</span></span> <span data-ttu-id="f9671-232">Por ejemplo, una nueva versión de su aplicación puede agregar un encabezado adicional a un mensaje.</span><span class="sxs-lookup"><span data-stu-id="f9671-232">For example, a new version of your application may add an extra header to a message.</span></span> <span data-ttu-id="f9671-233">A continuación, al enviar de la nueva versión a la anterior, el sistema debe tratar con un encabezado adicional, así como un encabezado de menos al ir en la otra dirección.</span><span class="sxs-lookup"><span data-stu-id="f9671-233">Then, when sending from the new version to the old, the system must deal with an extra header, as well as a missing header when going in the other direction.</span></span>  
  
 <span data-ttu-id="f9671-234">Las siguientes reglas se aplican a los encabezados de versiones:</span><span class="sxs-lookup"><span data-stu-id="f9671-234">The following rules apply for versioning headers:</span></span>  
  
- <span data-ttu-id="f9671-235">WCF no objeto a los encabezados que faltan; los miembros correspondientes se dejan con sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="f9671-235">WCF does not object to the missing headers—the corresponding members are left at their default values.</span></span>  
  
- <span data-ttu-id="f9671-236">WCF también omite encabezados adicionales inesperados.</span><span class="sxs-lookup"><span data-stu-id="f9671-236">WCF also ignores unexpected extra headers.</span></span> <span data-ttu-id="f9671-237">La única excepción a esta regla es si el encabezado adicional tiene un atributo `MustUnderstand` establecido en `true` en el mensaje SOAP entrante. En este caso, se produce una excepción porque no se puede procesar ningún encabezado que deba entenderse.</span><span class="sxs-lookup"><span data-stu-id="f9671-237">The one exception to this rule is if the extra header has a `MustUnderstand` attribute set to `true` in the incoming SOAP message—in this case, an exception is thrown because a header that must be understood cannot be processed.</span></span>  
  
 <span data-ttu-id="f9671-238">Los cuerpos de mensajes tienen reglas de versión similares; se omiten las partes de cuerpo de mensaje adicionales y que faltan.</span><span class="sxs-lookup"><span data-stu-id="f9671-238">Message bodies have similar versioning rules—both missing and additional message body parts are ignored.</span></span>  
  
## <a name="inheritance-considerations"></a><span data-ttu-id="f9671-239">Consideraciones sobre la herencia</span><span class="sxs-lookup"><span data-stu-id="f9671-239">Inheritance Considerations</span></span>  

 <span data-ttu-id="f9671-240">Un tipo de contrato de mensaje puede heredar de otro tipo, con tal de que el tipo base también tenga un contrato de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f9671-240">A message contract type can inherit from another type, as long as the base type also has a message contract.</span></span>  
  
 <span data-ttu-id="f9671-241">Al crear u obtener acceso a un mensaje utilizando un tipo de contrato de mensaje que hereda de otros tipos de contrato de mensaje, se aplican las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f9671-241">When creating or accessing a message using a message contract type that inherits from other message contract types, the following rules apply:</span></span>  
  
- <span data-ttu-id="f9671-242">Todos los encabezados del mensaje en la jerarquía de la herencia se unen para formar el conjunto completo de encabezados del mensaje.</span><span class="sxs-lookup"><span data-stu-id="f9671-242">All of the message headers in the inheritance hierarchy are collected together to form the full set of headers for the message.</span></span>  
  
- <span data-ttu-id="f9671-243">Todas las partes del cuerpo del mensaje en la jerarquía de la herencia se unen para formar el cuerpo del mensaje completo.</span><span class="sxs-lookup"><span data-stu-id="f9671-243">All of the message body parts in the inheritance hierarchy are collected together to form the full message body.</span></span> <span data-ttu-id="f9671-244">Las partes del cuerpo se ordenan de acuerdo con las reglas de clasificación normales (mediante la propiedad <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType> y, a continuación, alfabéticamente), sin importar su lugar en la jerarquía de herencia.</span><span class="sxs-lookup"><span data-stu-id="f9671-244">The body parts are ordered according to the usual ordering rules (by <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType> property and then alphabetical), with no relevance to their place in the inheritance hierarchy.</span></span> <span data-ttu-id="f9671-245">Se desaconseja en gran medida usar la herencia de contrato de mensaje donde las partes del cuerpo del mensaje tienen lugar en varios niveles del árbol de herencia.</span><span class="sxs-lookup"><span data-stu-id="f9671-245">Using message contract inheritance where message body parts occur at multiple levels of the inheritance tree is strongly discouraged.</span></span> <span data-ttu-id="f9671-246">Si una clase base y una clase derivada definen un encabezado o una parte del cuerpo con el mismo nombre, el miembro de la clase más base se utiliza para almacenar el valor de ese encabezado o parte del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="f9671-246">If a base class and a derived class define a header or a body part with the same name, the member from the base-most class is used to store the value of that header or body part.</span></span>  
  
 <span data-ttu-id="f9671-247">Considere las clases del siguiente ejemplo de código:</span><span class="sxs-lookup"><span data-stu-id="f9671-247">Consider the classes in the following code example.</span></span>  
  
```csharp  
[MessageContract]  
public class PersonRecord  
{  
  [MessageHeader(Name="ID")] public int personID;  
  [MessageBodyMember] public string patientName;  
}  
  
[MessageContract]  
public class PatientRecord : PersonRecord  
{  
  [MessageHeader(Name="ID")] public int patientID;  
  [MessageBodyMember] public string diagnosis;  
}  
```  
  
 <span data-ttu-id="f9671-248">La clase `PatientRecord` describe un mensaje con un encabezado denominado `ID`.</span><span class="sxs-lookup"><span data-stu-id="f9671-248">The `PatientRecord` class describes a message with one header called `ID`.</span></span> <span data-ttu-id="f9671-249">El encabezado corresponde a `personID` y no al miembro `patientID`, porque se elige el miembro más base.</span><span class="sxs-lookup"><span data-stu-id="f9671-249">The header corresponds to the `personID` and not the `patientID` member, because the base-most member is chosen.</span></span> <span data-ttu-id="f9671-250">Por lo tanto, el campo `patientID` es inútil en este caso.</span><span class="sxs-lookup"><span data-stu-id="f9671-250">Thus, the `patientID` field is useless in this case.</span></span> <span data-ttu-id="f9671-251">El cuerpo del mensaje contiene el elemento `diagnosis` seguido del elemento `patientName`, porque ése es el orden alfabético.</span><span class="sxs-lookup"><span data-stu-id="f9671-251">The body of the message contains the `diagnosis` element followed by the `patientName` element, because that is the alphabetical order.</span></span> <span data-ttu-id="f9671-252">Observe que el ejemplo muestra un patrón que se desaconseja fuertemente: la base y los contratos de mensaje derivados tienen partes del cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="f9671-252">Notice that the example shows a pattern that is strongly discouraged: both the base and the derived message contracts have message body parts.</span></span>  
  
## <a name="wsdl-considerations"></a><span data-ttu-id="f9671-253">Consideraciones sobre WSDL</span><span class="sxs-lookup"><span data-stu-id="f9671-253">WSDL Considerations</span></span>  

 <span data-ttu-id="f9671-254">Al generar un lenguaje de descripción de servicios Web (WSDL) a partir de un servicio que usa contratos de mensaje, es importante recordar que no todas las características de contratos de mensaje se reflejan en el WSDL resultante.</span><span class="sxs-lookup"><span data-stu-id="f9671-254">When generating a Web Services Description Language (WSDL) contract from a service that uses message contracts, it is important to remember that not all message contract features are reflected in the resulting WSDL.</span></span> <span data-ttu-id="f9671-255">Considere los siguientes puntos:</span><span class="sxs-lookup"><span data-stu-id="f9671-255">Consider the following points:</span></span>  
  
- <span data-ttu-id="f9671-256">WSDL no puede expresar el concepto de una matriz de encabezados.</span><span class="sxs-lookup"><span data-stu-id="f9671-256">WSDL cannot express the concept of an array of headers.</span></span> <span data-ttu-id="f9671-257">Al crear los mensajes con una matriz de encabezados utilizando <xref:System.ServiceModel.MessageHeaderArrayAttribute>, el WSDL resultante refleja solo un encabezado en lugar de la matriz.</span><span class="sxs-lookup"><span data-stu-id="f9671-257">When creating messages with an array of headers using the <xref:System.ServiceModel.MessageHeaderArrayAttribute>, the resulting WSDL reflects only one header instead of the array.</span></span>  
  
- <span data-ttu-id="f9671-258">El documento WSDL resultante puede que no refleje alguna información de protección.</span><span class="sxs-lookup"><span data-stu-id="f9671-258">The resulting WSDL document may not reflect some protection-level information.</span></span>  
  
- <span data-ttu-id="f9671-259">El tipo de mensaje generado en el WSDL tiene el mismo nombre que el nombre de clase del tipo de contrato de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f9671-259">The message type generated in the WSDL has the same name as the class name of the message contract type.</span></span>  
  
- <span data-ttu-id="f9671-260">Al utilizar el mismo contrato del mensaje en varias operaciones, se generan varios tipos de mensaje en el documento WSDL.</span><span class="sxs-lookup"><span data-stu-id="f9671-260">When using the same message contract in multiple operations, multiple message types are generated in the WSDL document.</span></span> <span data-ttu-id="f9671-261">Los nombres se hacen únicos sumando los números "2", "3", etc., para los usos subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="f9671-261">The names are made unique by adding the numbers "2", "3", and so on, for subsequent uses.</span></span> <span data-ttu-id="f9671-262">Al importar el WSDL, varios tipos de contrato de mensaje se crean y son idénticos salvo por sus nombres.</span><span class="sxs-lookup"><span data-stu-id="f9671-262">When importing back the WSDL, multiple message contract types are created and are identical except for their names.</span></span>  
  
## <a name="soap-encoding-considerations"></a><span data-ttu-id="f9671-263">Consideraciones sobre la codificación SOAP</span><span class="sxs-lookup"><span data-stu-id="f9671-263">SOAP Encoding Considerations</span></span>  

 <span data-ttu-id="f9671-264">WCF permite usar el estilo de codificación SOAP heredado de XML; sin embargo, no se recomienda su uso.</span><span class="sxs-lookup"><span data-stu-id="f9671-264">WCF allows you to use the legacy SOAP encoding style of XML, however, its use is not recommended.</span></span> <span data-ttu-id="f9671-265">Al utilizar este estilo (estableciendo la propiedad `Use` como `Encoded` en el <xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType> aplicado al contrato de servicio), las siguientes consideraciones adicionales se aplican:</span><span class="sxs-lookup"><span data-stu-id="f9671-265">When using this style (by setting the `Use` property to `Encoded` on the <xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType> applied to the service contract), the following additional considerations apply:</span></span>  
  
- <span data-ttu-id="f9671-266">No se admiten los encabezados del mensaje; esto significa que el atributo <xref:System.ServiceModel.MessageHeaderAttribute> y el atributo de matriz <xref:System.ServiceModel.MessageHeaderArrayAttribute> son incompatibles con la codificación SOAP.</span><span class="sxs-lookup"><span data-stu-id="f9671-266">The message headers are not supported; this means that the attribute <xref:System.ServiceModel.MessageHeaderAttribute> and the array attribute <xref:System.ServiceModel.MessageHeaderArrayAttribute> are incompatible with SOAP encoding.</span></span>  
  
- <span data-ttu-id="f9671-267">Si no se ajusta el contrato del mensaje, esto es, si la propiedad <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> está establecida como `false`, el contrato de mensaje solo puede tener una parte del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="f9671-267">If the message contract is not wrapped, that is, if the property <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> is set to `false`, the message contract can have only one body part.</span></span>  
  
- <span data-ttu-id="f9671-268">El nombre del elemento contenedor para el contrato del mensaje de solicitud debe coincidir con el nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="f9671-268">The name of the wrapper element for the request message contract must match the operation name.</span></span> <span data-ttu-id="f9671-269">Utilice la propiedad `WrapperName` del contrato del mensaje para ello.</span><span class="sxs-lookup"><span data-stu-id="f9671-269">Use the `WrapperName` property of the message contract for this.</span></span>  
  
- <span data-ttu-id="f9671-270">El nombre del elemento contenedor del contrato del mensaje de respuesta debe ser igual que el nombre de la operación con el sufijo “Respuesta” agregado.</span><span class="sxs-lookup"><span data-stu-id="f9671-270">The name of the wrapper element for the response message contract must be the same as the name of the operation suffixed by 'Response'.</span></span> <span data-ttu-id="f9671-271">Utilice la propiedad <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A> del contrato del mensaje para ello.</span><span class="sxs-lookup"><span data-stu-id="f9671-271">Use the <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A> property of the message contract for this.</span></span>  
  
- <span data-ttu-id="f9671-272">La codificación SOAP conserva las referencias a objetos.</span><span class="sxs-lookup"><span data-stu-id="f9671-272">SOAP encoding preserves object references.</span></span> <span data-ttu-id="f9671-273">Por ejemplo, considere el fragmento de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="f9671-273">For example, consider the following code.</span></span>  
  
    ```csharp  
    [MessageContract(WrapperName="updateChangeRecord")]  
    public class ChangeRecordRequest  
    {  
      [MessageBodyMember] Person changedBy;  
      [MessageBodyMember] Person changedFrom;  
      [MessageBodyMember] Person changedTo;  
    }  
  
    [MessageContract(WrapperName="updateChangeRecordResponse")]  
    public class ChangeRecordResponse  
    {  
      [MessageBodyMember] Person changedBy;  
      [MessageBodyMember] Person changedFrom;  
      [MessageBodyMember] Person changedTo;  
    }  
  
    // application code:  
    ChangeRecordRequest cr = new ChangeRecordRequest();  
    Person p = new Person("John Doe");  
    cr.changedBy=p;  
    cr.changedFrom=p;  
    cr.changedTo=p;  
    ```  
  
 <span data-ttu-id="f9671-274">Después de serializar el mensaje mediante codificación SOAP, `changedFrom` y `changedTo` no contienen sus propias copias de `p`; en su lugar, señalan la copia que está dentro del elemento `changedBy`.</span><span class="sxs-lookup"><span data-stu-id="f9671-274">After serializing the message using SOAP encoding, `changedFrom` and `changedTo` do not contain their own copies of `p`, but instead point to the copy inside the `changedBy` element.</span></span>  
  
## <a name="performance-considerations"></a><span data-ttu-id="f9671-275">Consideraciones de rendimiento</span><span class="sxs-lookup"><span data-stu-id="f9671-275">Performance Considerations</span></span>  

 <span data-ttu-id="f9671-276">Cada encabezado del mensaje y la parte del cuerpo del mensaje se serializa independientemente de las otras.</span><span class="sxs-lookup"><span data-stu-id="f9671-276">Every message header and message body part is serialized independently of the others.</span></span> <span data-ttu-id="f9671-277">Por tanto, los mismos espacios de nombres se pueden declarar de nuevo para cada encabezado y parte del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="f9671-277">Therefore, the same namespaces can be declared again for each header and body part.</span></span> <span data-ttu-id="f9671-278">Para mejorar el rendimiento, sobre todo en lo que se refiere al tamaño del mensaje en la conexión, consolide varios encabezados y partes de cuerpo en un único encabezado o parte del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="f9671-278">To improve performance, especially in terms of the size of the message on the wire, consolidate multiple headers and body parts into a single header or body part.</span></span> <span data-ttu-id="f9671-279">Por ejemplo, en lugar del siguiente código:</span><span class="sxs-lookup"><span data-stu-id="f9671-279">For example, instead of the following code:</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public Account sourceAccount;  
  [MessageBodyMember] public Account targetAccount;  
  [MessageBodyMember] public int amount;  
}  
```  
  
 <span data-ttu-id="f9671-280">Utilice este código:</span><span class="sxs-lookup"><span data-stu-id="f9671-280">Use this code.</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public OperationDetails details;  
}  
  
[DataContract]  
public class OperationDetails  
{  
  [DataMember] public Account sourceAccount;  
  [DataMember] public Account targetAccount;  
  [DataMember] public int amount;  
}  
```  
  
### <a name="event-based-asynchronous-and-message-contracts"></a><span data-ttu-id="f9671-281">Contratos de mensaje y asincrónicos basados en eventos</span><span class="sxs-lookup"><span data-stu-id="f9671-281">Event-based Asynchronous and Message Contracts</span></span>  

 <span data-ttu-id="f9671-282">Las directrices de diseño del modelo asincrónico basado en eventos afirman que si se devuelve más de un valor, uno de los valores se devuelve como propiedad `Result` y los demás se devuelven como propiedades del objeto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="f9671-282">The design guidelines for the event-based asynchronous model state that if more than one value is returned, one value is returned as the `Result` property and the others are returned as properties on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="f9671-283">De esto resulta que si un cliente importa metadatos mediante opciones de comando asincrónicas basadas en eventos y la operación devuelve más de un valor, el objeto <xref:System.EventArgs> predeterminado devuelve un valor como propiedad `Result` y el resto son propiedades del objeto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="f9671-283">One result of this is that if a client imports metadata using the event-based asynchronous command options and the operation returns more than one value, the default <xref:System.EventArgs> object returns one value as the `Result` property and the remainder are properties of the <xref:System.EventArgs> object.</span></span>  
  
 <span data-ttu-id="f9671-284">Si desea recibir el objeto del mensaje como propiedad `Result` y que los valores devueltos sean propiedades de ese objeto, utilice la opción de comando `/messageContract`.</span><span class="sxs-lookup"><span data-stu-id="f9671-284">If you want to receive the message object as the `Result` property and have the returned values as properties on that object, use the `/messageContract` command option.</span></span> <span data-ttu-id="f9671-285">Esto genera una firma que devuelve el mensaje de respuesta como la propiedad `Result` del objeto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="f9671-285">This generates a signature that returns the response message as the `Result` property on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="f9671-286">Todos los valores de devolución internos se convierten, pues, en propiedades del objeto de mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="f9671-286">All internal return values are then properties of the response message object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9671-287">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9671-287">See also</span></span>

- [<span data-ttu-id="f9671-288">Utilización de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="f9671-288">Using Data Contracts</span></span>](using-data-contracts.md)
- [<span data-ttu-id="f9671-289">Diseño e implementación de servicios</span><span class="sxs-lookup"><span data-stu-id="f9671-289">Designing and Implementing Services</span></span>](../designing-and-implementing-services.md)
