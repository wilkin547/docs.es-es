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
# <a name="how-to-set-the-protectionlevel-property"></a>Procedimiento para establecer la propiedad ProtectionLevel

Puede establecer el nivel de protección aplicando un atributo adecuado y estableciendo la propiedad. Puede establecer la protección en el nivel del servicio para que afecte a todas las partes de cada mensaje o puede establecer la protección en los niveles cada vez más individuales, desde los métodos a las partes del mensaje. Para obtener más información acerca de la `ProtectionLevel` propiedad, consulte [Descripción del nivel de protección](understanding-protection-level.md).  
  
> [!NOTE]
> Puede establecer niveles de protección solo mediante código, no mediante configuración.  
  
### <a name="to-sign-all-messages-for-a-service"></a>Para firmar todos los mensajes para un servicio  
  
1. Cree una interfaz para el servicio.  
  
2. Aplique el atributo <xref:System.ServiceModel.ServiceContractAttribute> al servicio y establezca la propiedad <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> en <xref:System.Net.Security.ProtectionLevel.Sign>, como se muestra en el código siguiente (el nivel predeterminado es <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>).  
  
     [!code-csharp[C_ProtectionLevel#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#1)]
     [!code-vb[C_ProtectionLevel#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#1)]  
  
### <a name="to-sign-all-message-parts-for-an-operation"></a>Para firmar todas las partes del mensaje para una operación  
  
1. Cree una interfaz para el servicio y aplique el atributo <xref:System.ServiceModel.ServiceContractAttribute> a la interfaz.  
  
2. Agregue una declaración de método a la interfaz.  
  
3. Aplique el atributo <xref:System.ServiceModel.OperationContractAttribute> al método, y establezca la propiedad <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> en <xref:System.Net.Security.ProtectionLevel.Sign>, como se muestra en el siguiente código.  
  
     [!code-csharp[C_ProtectionLevel#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#2)]
     [!code-vb[C_ProtectionLevel#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#2)]  
  
## <a name="protecting-fault-messages"></a>Protección de mensajes de error  

 Las excepciones que se producen en un servicio se pueden enviar a un cliente como errores de SOAP. Para obtener más información sobre cómo crear errores fuertemente tipados, vea [especificar y controlar errores en contratos y servicios](specifying-and-handling-faults-in-contracts-and-services.md) y [Cómo: declarar errores en contratos de servicio](how-to-declare-faults-in-service-contracts.md).  
  
#### <a name="to-protect-a-fault-message"></a>Para proteger un mensaje de error  
  
1. Cree un tipo que represente el mensaje de error. El ejemplo siguiente crea una clase denominada `MathFault` con dos campos.  
  
2. Aplique el atributo <xref:System.Runtime.Serialization.DataContractAttribute> al tipo y un atributo <xref:System.Runtime.Serialization.DataMemberAttribute> a cada campo que se debería serializar, como se muestra en el código siguiente.  
  
     [!code-csharp[C_ProtectionLevel#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#3)]
     [!code-vb[C_ProtectionLevel#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#3)]  
  
3. En la interfaz que devolverá el error, aplique el atributo <xref:System.ServiceModel.FaultContractAttribute> al método que devolverá el error y establezca el parámetro `detailType` en el tipo de la clase de error.  
  
4. También en el constructor, establezca la propiedad <xref:System.ServiceModel.FaultContractAttribute.ProtectionLevel%2A> en <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>, como se muestra en el código siguiente.  
  
     [!code-csharp[C_ProtectionLevel#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#4)]
     [!code-vb[C_ProtectionLevel#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#4)]  
  
## <a name="protecting-message-parts"></a>Protección de las partes del mensaje  

 Use un contrato de mensaje para proteger partes de un mensaje. Para obtener más información sobre los contratos de mensajes, vea [usar contratos de mensaje](./feature-details/using-message-contracts.md).  
  
#### <a name="to-protect-a-message-body"></a>Para proteger el cuerpo de un mensaje  
  
1. Cree un tipo que representa al mensaje. El siguiente ejemplo crea una clase `Company` con dos campos, `CompanyName` y `CompanyID`.  
  
2. Aplique el atributo <xref:System.ServiceModel.MessageContractAttribute> a la clase y establezca la propiedad <xref:System.ServiceModel.MessageContractAttribute.ProtectionLevel%2A> en <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.  
  
3. Aplique el atributo <xref:System.ServiceModel.MessageHeaderAttribute> a un campo que se expresará como un encabezado de mensaje y establezca la propiedad `ProtectionLevel` en <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.  
  
4. Aplique <xref:System.ServiceModel.MessageBodyMemberAttribute> a cualquier campo que se expresará como parte del cuerpo del mensaje y establezca la `ProtectionLevel` propiedad en <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> , como se muestra en el ejemplo siguiente.  
  
     [!code-csharp[C_ProtectionLevel#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#5)]
     [!code-vb[C_ProtectionLevel#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#5)]  
  
## <a name="example"></a>Ejemplo  

 El ejemplo siguiente establece la propiedad `ProtectionLevel` de varias clases de atributos en varios lugares de un servicio.  
  
 [!code-csharp[C_ProtectionLevel#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#6)]
 [!code-vb[C_ProtectionLevel#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#6)]  
  
## <a name="compiling-the-code"></a>Compilar el código  

 En el ejemplo de código siguiente se muestran los espacios de nombres requeridos para compilar el código de ejemplo.  
  
 [!code-csharp[C_ProtectionLevel#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#0)]
 [!code-vb[C_ProtectionLevel#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#0)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- <xref:System.ServiceModel.FaultContractAttribute>
- <xref:System.ServiceModel.MessageContractAttribute>
- <xref:System.ServiceModel.MessageBodyMemberAttribute>
- [Descripción de los niveles de protección](understanding-protection-level.md)
