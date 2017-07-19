---
title: "Serializaci&#243;n JSON | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# Serializaci&#243;n JSON
Este ejemplo muestra cómo utilizar <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> para serializar y deserializar los datos en el formato de notación de objetos JavaScript \(JSON\).Este motor de serialización convierte los datos de JSON en instancias de tipos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] y de nuevo en datos de JSON.<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> admite los mismos tipos que <xref:System.Runtime.Serialization.DataContractSerializer>.El formato de datos de JSON es especialmente útil al escribir JavaScript asincrónico y aplicaciones web de estilo XML \(AJAX\).La compatibilidad de AJAX en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] se optimiza para usarse con AJAX de ASP.NET a través del control ScriptManager.Para obtener ejemplos acerca de cómo usar [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] con ASP.NET AJAX, vea [AJAX Samples](http://msdn.microsoft.com/es-es/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 El ejemplo utiliza un contrato de datos `Person` para mostrar la serialización y deserialización.  
  
```  
[DataContract]  
    class Person  
    {  
        [DataMember]  
        internal string name;  
  
        [DataMember]  
        internal int age;  
    }  
  
```  
  
 Para serializar una instancia del tipo `Person` a JSON, cree primero <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> y utilice el método `WriteObject` para escribir los datos de JSON en una secuencia.  
  
```  
Person p = new Person();  
//Set up Person object...  
MemoryStream stream1 = new MemoryStream();  
DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
ser.WriteObject(stream1, p);  
  
```  
  
 La secuencia de la memoria contiene los datos de JSON válidos.  
  
```  
{“age”:42,”name”:”John”}  
  
```  
  
 El ejemplo muestra cómo deserializar a partir de datos de JSON en un objeto.Se rebobina la secuencia y se llama a `ReadObject`.  
  
```  
Person p2 = (Person)ser.ReadObject(stream1);  
```  
  
 Al examinar el objeto `p2`, se revela que se han deserializado los datos de JSON correctamente.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Compile la solución JsonSerialization.sln tal y como se describe en [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  Ejecute la aplicación de consola resultante.  
  
## Vea también