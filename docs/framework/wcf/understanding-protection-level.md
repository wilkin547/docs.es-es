---
title: Descripción de los niveles de protección
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, security
- ProtectionLevel property
ms.assetid: 0c034608-a1ac-4007-8287-b1382eaa8bf2
ms.openlocfilehash: 157e660a8b4d3866b9ab1994c409f82f16ac8359
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="understanding-protection-level"></a>Descripción de los niveles de protección
La propiedad `ProtectionLevel` se encuentra en muchas clases diferentes, como las clases <xref:System.ServiceModel.ServiceContractAttribute> y <xref:System.ServiceModel.OperationContractAttribute>. La propiedad controla cómo se protege una parte de un mensaje (o todo entero). Este tema explica la característica de Windows Communication Foundation (WCF) y cómo funciona.  
  
 Para obtener instrucciones acerca de cómo establecer el nivel de protección, consulte [Cómo: establecer la propiedad ProtectionLevel](../../../docs/framework/wcf/how-to-set-the-protectionlevel-property.md).  
  
> [!NOTE]
>  Los niveles de protección solo se pueden establecer en el código, no en la configuración.  
  
## <a name="basics"></a>Fundamentos  
 Para entender la característica de nivel de protección, se aplican las instrucciones básicas siguientes:  
  
-   Existen tres niveles básicos de protección para cualquier parte de un mensaje. La propiedad (dondequiera que se produzca) está establecida como uno de los valores de la enumeración <xref:System.Net.Security.ProtectionLevel>. En orden ascendente de protección, incluyen:  
  
    -   `None`.  
  
    -   `Sign`. La parte protegida está firmada digitalmente. De esta manera se garantiza la detección de cualquier modificación en la parte protegida del mensaje.  
  
    -   `EncryptAndSign`. La parte del mensaje se cifra para garantizar la confidencialidad antes de firmarse.  
  
-   Puede establecer los requisitos de protección para *datos de la aplicación* con esta característica. Por ejemplo, los encabezados de WS-Addressing son los datos de la infraestructura y, por consiguiente, no se verán afectados por `ProtectionLevel`.  
  
-   Cuando el modo de seguridad está establecido como `Transport`, el mecanismo de transporte protege el mensaje completo. Por consiguiente, establecer un nivel de protección independiente para las distintas partes de un mensaje no tendrá ningún efecto.  
  
-   El `ProtectionLevel` es una manera para que el programador establezca el *nivel mínimo* que debe cumplir un enlace. Cuando se implementa un servicio, el enlace real especificado en la configuración puede admitir o no el nivel mínimo. Por ejemplo, de forma predeterminada, la clase <xref:System.ServiceModel.BasicHttpBinding> no proporciona seguridad (aunque puede estar habilitada). Por consiguiente, utilizarlo con un contrato que tiene un valor distinto de `None` producirá una excepción.  
  
-   Si el servicio requiere que el mínimo `ProtectionLevel` para todos los mensajes es `Sign`, un cliente (quizás creado por una tecnología no WCF) puede cifrar y firmar todos los mensajes (que es mayor que el mínimo requerido). En este caso, WCF no iniciará una excepción porque el cliente ha hecho más que el mínimo. Sin embargo, tenga en cuenta que las aplicaciones de WCF (servicios o clientes) no sobreprotegerán una parte del mensaje si es posible pero cumplan con el nivel mínimo. Además, tenga en cuenta que al utilizar `Transport` como modo de seguridad, el transporte puede sobreproteger la secuencia de mensajes porque no puede proteger en un nivel más específico.  
  
-   Si establece `ProtectionLevel` como `Sign` o `EncryptAndSign`, deberá usar un enlace con la seguridad habilitada o se producirá una excepción.  
  
-   Si selecciona un enlace que habilita la seguridad y no establece la propiedad `ProtectionLevel` en cualquier parte del contrato, se cifrarán y firmarán todos los datos de la aplicación.  
  
-   Si selecciona un enlace que no tiene la seguridad habilitada (por ejemplo, la clase `BasicHttpBinding` tiene la seguridad deshabilitada de forma predeterminada) y no se establece `ProtectionLevel` explícitamente, no se protegerá ninguno de los datos de la aplicación.  
  
-   Si está utilizando un enlace que aplica la seguridad en el nivel de transporte, todos los datos de la aplicación se protegerán según las capacidades del transporte.  
  
-   Si utiliza un enlace que aplica la seguridad en el nivel de mensaje, a continuación, los datos de la aplicación se protegerán según los niveles de protección establecidos en el contrato. Si no especifica un nivel de protección, a continuación, se cifrarán y firmarán todos los datos de la aplicación en los mensajes.  
  
-   Se puede establecer `ProtectionLevel` en distintos niveles de ámbito. Hay una jerarquía asociada con el ámbito, que se explicará en la sección siguiente.  
  
## <a name="scoping"></a>Ámbito  
 Establecer `ProtectionLevel` en la API de nivel superior define el nivel para todos los niveles debajo de ella. Si `ProtectionLevel` está establecido con un valor diferente en un nivel más bajo, todas las API debajo de ese nivel en la jerarquía se restablecerán ahora en el nuevo nivel (sin embargo, las API por encima de él se seguirán viendo afectadas por el nivel superior). La jerarquía es la siguiente. Los atributos en el mismo nivel son del mismo nivel.  
  
 <xref:System.ServiceModel.ServiceContractAttribute>  
  
 <xref:System.ServiceModel.OperationContractAttribute>  
  
 <xref:System.ServiceModel.FaultContractAttribute>  
  
 <xref:System.ServiceModel.MessageContractAttribute>  
  
 <xref:System.ServiceModel.MessageHeaderAttribute>  
  
 <xref:System.ServiceModel.MessageBodyMemberAttribute>  
  
## <a name="programming-protectionlevel"></a>Programación de ProtectionLevel  
 Para programar `ProtectionLevel` en cualquier punto de la jerarquía, basta con establecer la propiedad con un valor adecuado cuando se aplique el atributo. Para obtener ejemplos, vea [Cómo: establecer la propiedad ProtectionLevel](../../../docs/framework/wcf/how-to-set-the-protectionlevel-property.md).  
  
> [!NOTE]
>  Establecer la propiedad en errores y contratos de mensaje exige conocer cómo funcionan esas características. Para obtener más información, consulte [Cómo: establecer la propiedad ProtectionLevel](../../../docs/framework/wcf/how-to-set-the-protectionlevel-property.md) y [usar contratos de mensaje](../../../docs/framework/wcf/feature-details/using-message-contracts.md).  
  
## <a name="ws-addressing-dependency"></a>Dependencia de WS-Addressing  
 En la mayoría de los casos, con el [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) generar un cliente se asegura de que los contratos de servicio y cliente sean idénticos. Sin embargo, los contratos aparentemente idénticos pueden hacer que el cliente produzca una excepción. Esto ocurre siempre que un enlace no admita la especificación de WS-Addressing y se especifiquen varios niveles de protección en el contrato. Por ejemplo, la clase <xref:System.ServiceModel.BasicHttpBinding> no admite la especificación o si crea un enlace personalizado que no admite WS-Addressing. La característica `ProtectionLevel` confía en la especificación de WS-Addressing para habilitar los niveles de protección diferentes en un contrato único. Si el enlace no admite la especificación de WS-Addressing, todos los niveles estarán establecidos en el mismo nivel de protección. El nivel de protección eficaz para todos los ámbitos del contrato estará establecido en el nivel de protección más alto utilizado en el contrato.  
  
 Esto puede producir un problema que será difícil depurar a primera vista. Es posible crear un contrato de cliente (una interfaz) que incluya los métodos para más de un servicio. Es decir, la misma interfaz se utiliza para crear un cliente que comunica con muchos servicios y la interfaz contiene los métodos para todos los servicios. El desarrollador debe tener cuidado en este escenario atípico para invocar solo aquellos métodos que son aplicables para cada servicio determinado. Si el enlace es la clase <xref:System.ServiceModel.BasicHttpBinding>, no se pueden admitir varios niveles de protección. Sin embargo, un servicio que responde al cliente podría responder a un cliente con un nivel de protección más bajo que el necesario. En este caso, el cliente producirá una excepción porque espera un nivel más alto.  
  
 El siguiente ejemplo del código muestra este problema. El ejemplo siguiente muestra un contrato de servicio y uno de cliente. Suponga que el enlace es el [ \<basicHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) elemento. Por consiguiente, todas las operaciones en un contrato tienen el mismo nivel de protección. Este nivel de protección uniforme se determina como el nivel de protección máximo en todas las operaciones.  
  
 El contrato de servicios es:  
  
 [!code-csharp[c_ProtectionLevel#7](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#7)]
 [!code-vb[c_ProtectionLevel#7](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#7)]  
  
 En el siguiente ejemplo de código se muestra una interfaz de contrato de cliente. Observe que incluye un método `Tax` que se utilizará con un servicio diferente:  
  
 [!code-csharp[c_ProtectionLevel#8](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#8)]
 [!code-vb[c_ProtectionLevel#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#8)]  
  
 Cuando el cliente llama al método `Price`, produce una excepción cuando recibe una respuesta del servicio. Esto se produce porque el cliente no especifica un `ProtectionLevel` en `ServiceContractAttribute` y, por consiguiente, el cliente utiliza el valor predeterminado (<xref:System.Net.Security.ProtectionLevel.EncryptAndSign>) para todos los métodos, incluido el método `Price`. Sin embargo, el servicio devuelve el valor mediante el nivel <xref:System.Net.Security.ProtectionLevel.Sign> porque el contrato de servicios define un método único que tiene el nivel de protección definido en <xref:System.Net.Security.ProtectionLevel.Sign>. En este caso, se producirá un error en el cliente al validar la respuesta del servicio.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>  
 <xref:System.ServiceModel.FaultContractAttribute>  
 <xref:System.ServiceModel.MessageContractAttribute>  
 <xref:System.ServiceModel.MessageHeaderAttribute>  
 <xref:System.ServiceModel.MessageBodyMemberAttribute>  
 <xref:System.Net.Security.ProtectionLevel>  
 [Seguridad de servicios](../../../docs/framework/wcf/securing-services.md)  
 [Cómo establecerla propiedad ProtectionLevel Property](../../../docs/framework/wcf/how-to-set-the-protectionlevel-property.md)  
 [Especificación y gestión de errores en contratos y servicios](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)  
 [Uso de contratos de mensaje](../../../docs/framework/wcf/feature-details/using-message-contracts.md)
