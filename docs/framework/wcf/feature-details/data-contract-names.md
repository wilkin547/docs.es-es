---
title: "Nombres de contratos de datos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "contratos de datos [WCF], asignación de nombres"
ms.assetid: 31f87e6c-247b-48f5-8e94-b9e1e33d8d09
caps.latest.revision: 27
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 27
---
# Nombres de contratos de datos
A veces un cliente y un servicio no comparten los mismos tipos.Todavía pueden pasar datos entre sí porque los contratos de datos son equivalentes en ambos lados.[Equivalencia del contrato de datos](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md) se basa en nombres de contrato de datos y de miembro de datos y por consiguiente se proporciona un mecanismo para asignar tipos y miembros a esos nombres.En este tema se explican las reglas para nombrar contratos de datos, así como el comportamiento predeterminado de la infraestructura de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] al crear los nombres.  
  
## Reglas básicas  
 Entre las reglas básicas con respecto a los nombres de los contratos de datos se incluyen:  
  
-   Un nombre de contrato de datos completo se compone de un espacio de nombres y de un nombre.  
  
-   Los miembros de datos solo tienen nombres, pero no espacios de nombres.  
  
-   Al procesar los contratos de datos, la infraestructura de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] distingue entre mayúsculas y minúsculas tanto en los espacios de nombres como en los nombres de contratos de datos y miembros de datos.  
  
## Espacios de nombres de contratos de datos  
 Un espacio de nombres de contrato de datos toma la forma de un Identificador uniforme de recursos \(URI\).El URI puede ser absoluto o relativo.De forma predeterminada, se asigna un espacio de nombres que procede del espacio de nombres de Common Language Runtime \(CLR\) de ese tipo a los contratos de datos de un tipo determinado.  
  
 De forma predeterminada, cualquier espacio de nombres CLR \(con el formato *Clr.Namespace*\) se asigna al espacio de nombres "http:\/\/schemas.datacontract.org\/2004\/07\/Clr.Namespace".Para invalidar este valor predeterminado, aplique el atributo <xref:System.Runtime.Serialization.ContractNamespaceAttribute> al ensamblado o módulo completo.De manera alternativa, para controlar el espacio de nombres del contrato de datos de cada tipo, establezca la propiedad <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A> del <xref:System.Runtime.Serialization.DataContractAttribute>.  
  
> [!NOTE]
>  El espacio de nombres "Http:\/\/schemas.microsoft.com\/2003\/10\/Serialization” está reservado y no se puede utilizar como un espacio de nombres de contrato de datos.  
  
> [!NOTE]
>  No puede invalidar el espacio de nombres predeterminado en tipos de contratos de datos que contengan declaraciones `delegate`.  
  
## Nombres de contratos de datos  
 El nombre predeterminado de un contrato de datos de un tipo determinado es el nombre de ese tipo.Para invalidar el valor predeterminado, establezca la propiedad <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> del <xref:System.Runtime.Serialization.DataContractAttribute> en un nombre alternativo.Más adelante, en este tema, se describen las reglas especiales de los tipos genéricos, en la sección "Nombres de contratos de datos para tipos genéricos".  
  
## Nombres de miembros de datos  
 El nombre predeterminado de un miembro de datos de un campo o propiedad determinado es el nombre de ese campo o propiedad.Para invalidar el valor predeterminado, establezca la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.Name%2A> del <xref:System.Runtime.Serialization.DataMemberAttribute> en un valor alternativo.  
  
### Ejemplos  
 El siguiente ejemplo muestra cómo puede invalidar el comportamiento de denominación predeterminado de contratos de datos y miembros de datos.  
  
 [!code-csharp[C_DataContractNames#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#1)]
 [!code-vb[C_DataContractNames#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#1)]  
  
## Nombres de contratos de datos para tipos genéricos  
 Existen reglas especiales para determinar los nombres de contratos de datos para tipos genéricos.Estas reglas ayudan a evitar las coincidencias de nombres de contratos de datos entre dos genéricos cerrados del mismo tipo genérico.  
  
 De forma predeterminada, el nombre del contrato de datos de un tipo genérico es el nombre del tipo, seguido por la cadena "Of", seguido por los nombres de contratos de datos de los parámetros genéricos, seguido por un *hash* calculado mediante los espacios de nombres de contrato de datos de los parámetros genéricos.Un hash es el resultado de una función matemática que actúa como una "huella" que identifica identifica de manera única una parte de datos.Cuando todos los parámetros genéricos son de tipo primitivo, se omite el hash.  
  
 Por ejemplo, vea los tipos del ejemplo siguiente.  
  
 [!code-csharp[C_DataContractNames#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#2)]
 [!code-vb[C_DataContractNames#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#2)]  
  
 En este ejemplo, el tipo `Drawing<Square,RegularRedBrush>` tiene el nombre de contrato de datos "DrawingOfSquareRedBrush5HWGAU6h", donde "5HWGAU6h" es un hash de los espacios de nombres "urn:default" y "urn:shapes".El tipo `Drawing<Square,SpecialRedBrush>` tiene el nombre de contrato de datos "DrawingOfSquareRedBrushjpB5LgQ\_S", donde "jpB5LgQ\_S" es un hash de los espacios de nombres "urn:shapes" y "urn:special".Tenga en cuenta que, si no se utiliza el hash, los dos nombres son idénticos y se produce un conflicto de nombres.  
  
## Personalización de los nombres de contratos de datos para tipos genéricos  
 A veces, los nombres de contrato de datos generados para tipos genéricos, como se describió previamente, son inaceptables.Por ejemplo, puede conocer de antemano que no se encontrará con nombres coincidentes y puede que desee eliminar el hash.En este caso, puede utilizar la propiedad <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> del atributo `DataContractAttribute` para especificar una manera diferente de generar los nombres.Puede utilizar números dentro de llaves dentro de la propiedad `Name` para hacer referencia a los nombres de contratos de datos de los parámetros genéricos.\(0 hace referencia al primer parámetro, 1 hace referencia al segundo, etc.\). Puede utilizar una almohadilla \(\#\) dentro de llaves para hacer referencia al hash.Puede utilizar cada una de estas referencias varias veces o ninguna.  
  
 Por ejemplo, el tipo genérico `Drawing` anterior podría haberse declarado como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[c_DataContractNames#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#3)]
 [!code-vb[c_DataContractNames#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#3)]  
  
 En este caso, el tipo `Drawing<Square,RegularRedBrush>` tiene del el nombre de contrato de datos "Drawing\_using\_RedBrush\_brush\_and\_Square\_shape".Tenga en cuenta que porque hay un "{\#}" en la propiedad <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A>, el hash no forma parte del nombre y por esto el tipo es susceptible a las coincidencias de nombres; por ejemplo, el tipo `Drawing<Square,SpecialRedBrush>` tendría exactamente el mismo nombre de contrato de datos.  
  
## Vea también  
 <xref:System.Runtime.Serialization.DataContractAttribute>   
 <xref:System.Runtime.Serialization.DataMemberAttribute>   
 <xref:System.Runtime.Serialization.ContractNamespaceAttribute>   
 [Utilización de contratos de datos](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)   
 [Equivalencia del contrato de datos](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)   
 [Data Contract Names](../../../../docs/framework/wcf/feature-details/data-contract-names.md)   
 [Versiones de contratos de datos](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md)