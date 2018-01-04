---
title: Utilizar DataContractSerializer y DataContractResolver para proporcionar la funcionalidad de NetDataContractSerializer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1376658f-f695-45f7-a7e0-94664e9619ff
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5477f11b5bc00ff4816b3fac8d61b254ebaf5ba0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="using-datacontractserializer-and-datacontractresolver-to-provide-the-functionality-of-netdatacontractserializer"></a>Utilizar DataContractSerializer y DataContractResolver para proporcionar la funcionalidad de NetDataContractSerializer
En este ejemplo se muestra el modo en que el uso de un <xref:System.Runtime.Serialization.DataContractSerializer> con un <xref:System.Runtime.Serialization.DataContractResolver> adecuado proporciona la misma funcionalidad que <xref:System.Runtime.Serialization.NetDataContractSerializer>. En este ejemplo se muestra cómo crear el <xref:System.Runtime.Serialization.DataContractResolver> adecuado y cómo agregarlo a <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 <xref:System.Runtime.Serialization.NetDataContractSerializer> difiere de <xref:System.Runtime.Serialization.DataContractSerializer> en un aspecto importante: <xref:System.Runtime.Serialization.NetDataContractSerializer> incluye información de tipos CLR en el XML serializado, mientras que <xref:System.Runtime.Serialization.DataContractSerializer> no. Por lo tanto, solo se puede utilizar <xref:System.Runtime.Serialization.NetDataContractSerializer> si ambos extremos, los de la serialización y los de la deserialización, comparten los mismos tipos de CLR. Sin embargo, se recomienda utilizar <xref:System.Runtime.Serialization.DataContractSerializer> porque su rendimiento es mejor que el de <xref:System.Runtime.Serialization.NetDataContractSerializer>. Puede cambiar la información que se serializa en <xref:System.Runtime.Serialization.DataContractSerializer> agregando un <xref:System.Runtime.Serialization.DataContractResolver> a él.  
  
 Este ejemplo consta de dos proyectos. El primer proyecto utiliza <xref:System.Runtime.Serialization.NetDataContractSerializer> para serializar un objeto. El segundo proyecto utiliza <xref:System.Runtime.Serialization.DataContractSerializer> con <xref:System.Runtime.Serialization.DataContractResolver> para proporcionar la misma funcionalidad que el primer proyecto.  
  
 El siguiente ejemplo de código muestra la implementación de un <xref:System.Runtime.Serialization.DataContractResolver> personalizado denominado `MyDataContractResolver` que se agrega a <xref:System.Runtime.Serialization.DataContractSerializer> en el proyecto DCSwithDCR.  
  
```  
class MyDataContractResolver : DataContractResolver  
{  
    private XmlDictionary dictionary = new XmlDictionary();  
  
    public MyDataContractResolver()  
    {  
    }  
  
    // Used at deserialization  
    // Allows users to map xsi:type name to any Type   
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)  
    {  
        Type type = knownTypeResolver.ResolveName(typeName, typeNamespace, null);  
        if (type == null)  
        {  
            type = Type.GetType(typeName + ", " + typeNamespace);  
        }  
        return type;  
    }  
  
    // Used at serialization  
    // Maps any Type to a new xsi:type representation  
    public override void ResolveType(Type dataContractType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)  
    {  
        knownTypeResolver.ResolveType(dataContractType, null, out typeName, out typeNamespace);  
        if (typeName == null || typeNamespace == null)  
        {  
            XmlDictionary dictionary = new XmlDictionary();  
            typeName = dictionary.Add(dataContractType.FullName);  
            typeNamespace = dictionary.Add(dataContractType.Assembly.FullName);  
        }  
    }  
}  
```  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Abra el archivo de CDRSample.sln con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Haga clic en el archivo de solución y elija **propiedades**.  
  
3.  En el **páginas de propiedades de solución** cuadro de diálogo, en **propiedades comunes**, **proyecto de inicio**, seleccione **varios proyectos de inicio:**.  
  
4.  Junto a la **DCSwithDCR** proyecto, seleccione **iniciar** desde el **acción** lista desplegable.  
  
5.  Junto a la **NetDCS** proyecto, seleccione **iniciar** desde el **acción** lista desplegable.  
  
6.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
7.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
8.  Para ejecutar la solución, presione CTRL+F5.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\NetDcSasDcSwithDCR`  
  
## <a name="see-also"></a>Vea también
