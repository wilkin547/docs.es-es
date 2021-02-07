---
description: Más información acerca de cómo especificar y controlar errores en contratos y servicios
title: Especificación y administración de errores en contratos y servicios
ms.date: 03/30/2017
helpviewer_keywords:
- handling faults [WCF]
ms.assetid: a9696563-d404-4905-942d-1e0834c26dea
ms.openlocfilehash: 32a1c795d2be964ff5da259b70a5695ddedfadb2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99676396"
---
# <a name="specifying-and-handling-faults-in-contracts-and-services"></a>Especificación y administración de errores en contratos y servicios

Las aplicaciones de Windows Communication Foundation (WCF) controlan las situaciones de error mediante la asignación de objetos de excepción administrados a objetos de error de SOAP y objetos de error de SOAP a objetos de excepción administrados. Los temas de esta sección describen cómo diseñar contratos para exponer condiciones de error como errores de SOAP personalizados, cómo devolver tales errores como parte de la implementación del servicio y cómo los clientes detectan tales errores.

## <a name="error-handling-overview"></a>Información general sobre control de errores

En todas las aplicaciones administradas, los errores de procesamiento están representados mediante objetos <xref:System.Exception>. En aplicaciones basadas en SOAP, como las aplicaciones WCF, los métodos de servicio comunican la información de errores de procesamiento mediante mensajes de error SOAP. Los errores SOAP son tipos de mensaje que se incluyen en los metadatos de una operación de servicio y, por consiguiente, crean un contrato de error que los clientes pueden utilizar para que su operación sea más sólida o interactiva. Además, dado que los errores de SOAP se expresan en los clientes en formato XML, es un sistema de tipos altamente interoperable que los clientes de cualquier plataforma SOAP pueden utilizar, lo que aumenta el alcance de la aplicación WCF.

Dado que las aplicaciones WCF se ejecutan en ambos tipos de sistemas de error, cualquier información de excepción administrada que se envíe al cliente debe convertirse de excepciones a errores de SOAP en el servicio, enviarse y convertirse de errores de SOAP a excepciones de error en clientes de WCF. En el caso de los clientes dúplex, los contratos de cliente también pueden devolver errores SOAP a un servicio. En cualquier caso, puede usar los comportamientos de excepción de servicio predeterminados o controlar explícitamente si (y cómo) se asignan las excepciones a los mensajes de error.

Se pueden enviar dos tipos de errores de SOAP: *declarados* y no *declarados*. Los errores SOAP declarados son aquéllos en los que una operación tiene un atributo <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> que especifica un tipo de error SOAP personalizado. No *declarado* Los errores de SOAP no se especifican en el contrato de una operación.

Se recomienda encarecidamente que las operaciones de servicio declaren sus errores mediante el atributo <xref:System.ServiceModel.FaultContractAttribute> para especificar formalmente todos los errores de SOAP que un cliente puede esperar recibir en el curso normal de una operación. Además, se recomienda que solo devuelva en un error SOAP la información que un cliente deba conocer para minimizar la divulgación de información.

Normalmente, los servicios (y los clientes dúplex) dan los siguientes pasos para integrar correctamente el control de errores en sus aplicaciones:

- Asignación de condiciones de excepción a errores SOAP personalizados.

- Los clientes y servicios envían y reciben errores SOAP como excepciones.

Además, los clientes y servicios de WCF pueden usar errores de SOAP no declarados con fines de depuración y pueden extender el comportamiento de error predeterminado. Las secciones siguientes tratan estas tareas y conceptos.

## <a name="map-exceptions-to-soap-faults"></a>Asignación de excepciones a errores SOAP

El primer paso para crear una operación que administra condiciones de error es decidir bajo qué condiciones una aplicación de cliente debería informar sobre errores. Algunas operaciones tienen condiciones de error específicas de su funcionalidad. Por ejemplo, una operación `PurchaseOrder` podría devolver la información concreta a los clientes a los que ya no se les permite iniciar una orden de compra. En otros casos, como un servicio `Calculator`, un error de SOAP `MathFault` más general puede ser capaz de describir todas las condiciones de error en un servicio completo. Una vez que se identifican las condiciones de error de los clientes del servicio, se puede construir un error SOAP personalizado y la operación se puede marcar para que devuelva ese error SOAP cuando se produzca la condición de error correspondiente.

Para obtener más información sobre este paso del desarrollo de un servicio o cliente, vea [definir y especificar errores](defining-and-specifying-faults.md).

## <a name="clients-and-services-handle-soap-faults-as-exceptions"></a>Los clientes y servicios administran los errores SOAP como excepciones

La identificación de condiciones de error de operación, la definición de errores de SOAP personalizados y el marcado de esas operaciones como la devolución de estos errores son los primeros pasos en el control de errores correcto en las aplicaciones WCF. El siguiente paso es implementar correctamente el envío y la recepción de estos errores. Normalmente, los servicios envían errores para informar a las aplicaciones de cliente sobre las condiciones de error, pero los clientes dúplex también pueden enviar errores SOAP a los servicios.

Para obtener más información, consulte [envío y recepción de errores](sending-and-receiving-faults.md).

## <a name="undeclared-soap-faults-and-debugging"></a>Errores de SOAP no declarados y depuración

Los errores de SOAP declarados son sumamente útiles para crear aplicaciones robustas, interoperables y distribuidas. Sin embargo, en algunos casos es útil para un servicio (o cliente dúplex) enviar un error SOAP no declarado, uno que no se menciona en el Lenguaje de descripción de servicios Web (WSDL) para esa operación. Por ejemplo, al desarrollar un servicio, pueden producirse situaciones inesperadas en las que es útil enviar información de vuelta al cliente para la depuración. Además, puede establecer la <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> propiedad o la <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> propiedad en `true` para permitir que los clientes de WCF obtengan información sobre las excepciones de operación de servicio internas. El envío de errores individuales y el establecimiento de las propiedades de comportamiento de depuración se describen en [envío y recepción de errores](sending-and-receiving-faults.md).

> [!IMPORTANT]
> Dado que las excepciones administradas pueden exponer información interna de la aplicación, establecer <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> o <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> en `true` puede permitir que los clientes de WCF obtengan información sobre las excepciones de operaciones de servicio internas, incluida la información de identificación personal u otra información confidencial.
>
> Por consiguiente, establecer <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> o <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> en `true` solo se recomienda como una manera de depurar temporalmente una aplicación de servicio. Además, el WSDL de un método que devuelve excepciones administradas no controladas de esta manera no contiene el contrato para la <xref:System.ServiceModel.FaultException%601> de tipo <xref:System.ServiceModel.ExceptionDetail>. Los clientes deben esperar la posibilidad de un error de SOAP desconocido (devuelto a los clientes de WCF como <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> objetos) para obtener la información de depuración correctamente.

## <a name="customizing-error-handling-with-ierrorhandler"></a>Personalización del control de errores con IErrorHandler

Si tiene requisitos especiales para personalizar el mensaje de respuesta al cliente cuando se produzca una excepción en el nivel de aplicación o para realizar algún procesamiento personalizado una vez devuelto el mensaje de respuesta, implemente la interfaz  <xref:System.ServiceModel.Dispatcher.IErrorHandler?displayProperty=nameWithType>.

## <a name="fault-serialization-issues"></a>Problemas de serialización de error

Cuando se deserializa un contrato de error, primero WCF intenta hacer coincidir el nombre del contrato de error del mensaje SOAP con el tipo de contrato de error. Si no puede encontrar una coincidencia exacta, buscará en orden alfabético un tipo compatible en la lista de contratos de error disponibles. Si dos contratos de error tienen tipos compatibles (uno es una subclase del otro, por ejemplo), se puede usar el tipo incorrecto para deserializar el error. Esto solo ocurre si el contrato de error no especifica ningún nombre, espacio de nombres ni acción. Para evitar que se produzca este problema, califique siempre completamente los contratos de error especificando los atributos de nombre, espacio de nombres y acción. Además, si ha definido muchos contratos de error relacionados derivados de una clase base compartida, asegúrese de marcar todos los miembros nuevos con `[DataMember(IsRequired=true)]`. Para obtener más información sobre este atributo `IsRequired`, vea <xref:System.Runtime.Serialization.DataMemberAttribute>. De esta forma, se evitará que una clase base sea de un tipo compatible y forzará la deserialización del error en el tipo derivado correcto.

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.FaultException>
- <xref:System.ServiceModel.FaultContractAttribute>
- <xref:System.ServiceModel.FaultException>
- <xref:System.Xml.Serialization.XmlSerializer>
- <xref:System.ServiceModel.XmlSerializerFormatAttribute>
- <xref:System.ServiceModel.FaultContractAttribute>
- <xref:System.ServiceModel.CommunicationException>
- <xref:System.ServiceModel.FaultContractAttribute.Action%2A>
- <xref:System.ServiceModel.FaultException.Code%2A>
- <xref:System.ServiceModel.FaultException.Reason%2A>
- <xref:System.ServiceModel.FaultCode.SubCode%2A>
- <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>
- [Definición y especificación de errores](defining-and-specifying-faults.md)
