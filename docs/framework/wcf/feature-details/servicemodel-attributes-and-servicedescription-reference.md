---
title: Atributos ServiceModel y referencia ServiceDescription
ms.date: 03/30/2017
ms.assetid: 4ab86b17-eab9-4846-a881-0099f9a7cc64
ms.openlocfilehash: 5e39a63d399edccc580b27ad4bfbc9ab05015ef9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600353"
---
# <a name="servicemodel-attributes-and-servicedescription-reference"></a>Atributos ServiceModel y referencia ServiceDescription
El *árbol de Descripción* es la jerarquía de tipos (a partir de la <xref:System.ServiceModel.Description.ServiceDescription?displayProperty=nameWithType> clase) que juntos describen todos los aspectos de un servicio. Windows Communication Foundation (WCF) usa un árbol de descripción para compilar un tiempo de ejecución de servicio válido, para publicar el lenguaje de descripción de servicios web (WSDL), el lenguaje de definición de esquemas XML (XSD) y las aserciones de directiva (metadatos) sobre el servicio que los clientes pueden usar para conectarse al servicio y usarlo, y para generar diversas representaciones de archivos de código y configuración  
  
 En este tema se describe cómo las propiedades relacionadas con contrato se obtienen del contrato de servicios, y cómo se implementan y agregan al árbol de descripción. En algunos casos, los valores de atributo se convierten en propiedades del comportamiento y el comportamiento se inserta en el árbol de descripción. Para obtener más información sobre cómo se convierten los valores del árbol de descripción en metadatos, vea [ServiceDescription y referencia de WSDL](servicedescription-and-wsdl-reference.md).  
  
## <a name="mapping-operations-to-the-description-tree"></a>Asignación de operaciones al árbol de descripción  
 En las aplicaciones WCF, los contratos de servicio se modelan mediante interfaces (o clases) que usan atributos para marcar la interfaz o la clase y sus métodos como una agrupación de operaciones. Cuando se abre una clase <xref:System.ServiceModel.ServiceHost>, las implementaciones y contratos de servicios se reflejan y combinan con información de configuración en un árbol de descripción.  
  
 Hay dos tipos de modelos de operación: el modelo de *parámetros* y el modelo de *contrato de mensaje* . El modelo de parámetro usa métodos administrados que no tienen un parámetro o tipo de valor devuelto que esté marcado por la clase <xref:System.ServiceModel.MessageContractAttribute?displayProperty=nameWithType>. En este modelo, los desarrolladores controlan la serialización de los parámetros y los valores devueltos, pero WCF genera los valores que se usan para rellenar el árbol de Descripción del servicio y su contrato.  
  
 Los enlaces especificados en archivos de configuración se cargan directamente en la propiedad <xref:System.ServiceModel.Description.ServiceEndpoint.Binding%2A?displayProperty=nameWithType>.  
  
|Propiedad ServiceBehaviorAttribute|Valor del árbol de descripción afectado|  
|---------------------------------------|-------------------------------------|  
|Nombre|<xref:System.ServiceModel.Description.ServiceDescription.Name%2A>|  
|Espacio de nombres|<xref:System.ServiceModel.Description.ServiceDescription.Namespace%2A>|  
|ConfigurationName|<xref:System.ServiceModel.Description.ServiceDescription.ConfigurationName%2A>|  
|IgnoreExtensionDataObject|Establece la propiedad <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.IgnoreExtensionDataObject%2A> para todas las operaciones.|  
|MaxItemsInObjectGraph|Establece la propiedad <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.MaxItemsInObjectGraph%2A> para todas las operaciones.|  
  
|Propiedad ServiceContractAttribute|Valor del árbol de descripción afectado|  
|---------------------------------------|-------------------------------------|  
|CallbackContract|<xref:System.ServiceModel.Description.ContractDescription.CallbackContractType%2A>, <xref:System.ServiceModel.Description.MessageDescription> agregó a todas las operaciones <xref:System.ServiceModel.Description.OperationDescription.Messages%2A>.|  
|ConfigurationName|<xref:System.ServiceModel.Description.ContractDescription.ConfigurationName%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.ContractDescription.ProtectionLevel%2A> y posiblemente niveles secundarios de protección. Para obtener más información acerca de la jerarquía de nivel de protección, vea [Descripción del nivel de protección](../understanding-protection-level.md).|  
|SessionMode|<xref:System.ServiceModel.Description.ContractDescription.SessionMode%2A>|  
  
|Valor ServiceKnownTypesAttribute|Valor del árbol de descripción afectado|  
|--------------------------------------|-------------------------------------|  
|MethodName|<xref:System.ServiceModel.Description.OperationDescription.KnownTypes%2A>|  
  
|Valor OperationContractAttribute|Valor del árbol de descripción afectado|  
|--------------------------------------|-------------------------------------|  
|Acción|<xref:System.ServiceModel.Description.MessageDescription.Action%2A> para el mensaje de salida o de entrada, dependiendo del contrato/contrato de devolución de llamada.|  
|AsyncPattern|Si es true, <xref:System.ServiceModel.Description.OperationDescription.BeginMethod%2A> y <xref:System.ServiceModel.Description.OperationDescription.EndMethod%2A>|  
|IsOneWay|Se asigna a una sola <xref:System.ServiceModel.Description.MessageDescription> en <xref:System.ServiceModel.Description.OperationDescription.Messages%2A>|  
|IsInitiating|<xref:System.ServiceModel.Description.OperationDescription.IsInitiating%2A>|  
|IsTerminating|<xref:System.ServiceModel.Description.OperationDescription.IsTerminating%2A>|  
|Nombre|<xref:System.ServiceModel.Description.OperationDescription.Name%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.OperationDescription.ProtectionLevel%2A> y posiblemente niveles secundarios de protección. Para obtener más información acerca de la jerarquía de nivel de protección, vea [Descripción del nivel de protección](../understanding-protection-level.md).|  
|ReplyAction|<xref:System.ServiceModel.Description.MessageDescription.Action%2A> para el mensaje de salida o de entrada, dependiendo del contrato/contrato de devolución de llamada.|  
  
|Valor FaultContractAttribute|Valor del árbol de descripción afectado|  
|----------------------------------|-------------------------------------|  
|Acción|<xref:System.ServiceModel.Description.FaultDescription.Action%2A> dependiendo del contrato/contrato de devolución de llamada.|  
|DetailType|<xref:System.ServiceModel.Description.FaultDescription.DetailType%2A>|  
|Nombre|<xref:System.ServiceModel.Description.FaultDescription.Name%2A>|  
|Espacio de nombres|<xref:System.ServiceModel.Description.FaultDescription.Namespace%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.FaultDescription.ProtectionLevel%2A>|  
  
|Valor DataContractFormatAttribute|Valor del árbol de descripción afectado|  
|---------------------------------------|-------------------------------------|  
|Uso|El valor <xref:System.ServiceModel.DataContractFormatAttribute.Style%2A> está definido en el <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> de la operación.|  
  
|Valor XmlSerializerFormatAttribute|Valor del árbol de descripción afectado|  
|----------------------------------------|-------------------------------------|  
|Estilo|Esta propiedad <xref:System.ServiceModel.XmlSerializerFormatAttribute> está definida en el <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> de la operación.|  
|Uso|El <xref:System.ServiceModel.XmlSerializerFormatAttribute> está definido en el <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> de la operación.|  
  
|Valor TransactionFlowAttribute|Valor del árbol de descripción afectado|  
|------------------------------------|-------------------------------------|  
|TransactionFlowOption|El <xref:System.ServiceModel.TransactionFlowAttribute> se agrega como un comportamiento de operación para la propiedad <xref:System.ServiceModel.Description.OperationDescription.Behaviors%2A>.|  
  
|Valor MessageContractAttribute|Valor del árbol de descripción afectado|  
|------------------------------------|-------------------------------------|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessageDescription.ProtectionLevel%2A>|  
|WrapperName|<xref:System.ServiceModel.Description.MessageBodyDescription.WrapperName%2A>|  
|WrapperNamespace|<xref:System.ServiceModel.Description.MessageBodyDescription.WrapperNamespace%2A>|  
  
|Valor MessageHeaderAttribute|Valor del árbol de descripción afectado|  
|----------------------------------|-------------------------------------|  
|Actor|<xref:System.ServiceModel.Description.MessageHeaderDescription.Actor%2A>para el encabezado correspondiente en<xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|MustUnderstand|<xref:System.ServiceModel.Description.MessageHeaderDescription.MustUnderstand%2A>para el encabezado correspondiente en<xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|Nombre|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>para el encabezado correspondiente en<xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|Espacio de nombres|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A>para el encabezado correspondiente en<xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A>para el encabezado correspondiente en<xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|Retransmisión|<xref:System.ServiceModel.Description.MessageHeaderDescription.Relay%2A>para el encabezado correspondiente en<xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
  
|Valor MessageBodyMemberAttribute|Valor del árbol de descripción afectado|  
|--------------------------------------|-------------------------------------|  
|Nombre|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>para la parte correspondiente en<xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|Espacio de nombres|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A>para la parte correspondiente en<xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|Pedido de|<xref:System.ServiceModel.Description.MessagePartDescription.Index%2A>para la parte correspondiente en<xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A>para la parte correspondiente en<xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
  
|Valor MessageHeaderArrayAttribute|Valor del árbol de descripción afectado|  
|---------------------------------------|-------------------------------------|  
|Actor|<xref:System.ServiceModel.Description.MessageHeaderDescription.Actor%2A>|  
|MustUnderstand|<xref:System.ServiceModel.Description.MessageHeaderDescription.MustUnderstand%2A>|  
|Nombre|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>|  
|Espacio de nombres|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A>|  
|Retransmisión|<xref:System.ServiceModel.Description.MessageHeaderDescription.Relay%2A>|  
  
|Valor MessagePropertyAttribute|Valor del árbol de descripción afectado|  
|------------------------------------|-------------------------------------|  
|Nombre|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>|  
  
|Valor MessageParameterAttribute|Valor del árbol de descripción afectado|  
|-------------------------------------|-------------------------------------|  
|Nombre|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>para la parte correspondiente en<xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
  
 Para obtener más información sobre cómo se convierten los valores del árbol de descripción en metadatos, vea [ServiceDescription y referencia de WSDL](servicedescription-and-wsdl-reference.md).  
  
## <a name="see-also"></a>Vea también

- [ServiceDescription y referencias WSDL](servicedescription-and-wsdl-reference.md)
