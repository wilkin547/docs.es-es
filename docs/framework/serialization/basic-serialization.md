---
title: "Serializaci&#243;n b&#225;sica | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "serialización binaria, serialización básica"
  - "serialización, serialización básica"
ms.assetid: d899d43c-335a-433e-a589-cd187192984f
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Serializaci&#243;n b&#225;sica
La manera más fácil de hacer una clase serializable es marcarla con el atributo [Serializable](frlrfSystemSerializableAttributeClassTopic) como sigue.  
  
```csharp  
[Serializable]  
public class MyObject {  
  public int n1 = 0;  
  public int n2 = 0;  
  public String str = null;  
}  
```  
  
 El ejemplo de código siguiente muestra cómo una instancia de esta clase se puede serializar a un archivo.  
  
```csharp  
MyObject obj = new MyObject();  
obj.n1 = 1;  
obj.n2 = 24;  
obj.str = "Some String";  
IFormatter formatter = new BinaryFormatter();  
Stream stream = new FileStream("MyFile.bin", FileMode.Create, FileAccess.Write, FileShare.None);  
formatter.Serialize(stream, obj);  
stream.Close();  
```  
  
 Este ejemplo utiliza un formateador binario para hacer la serialización.Todo lo que necesita hacer es crear una instancia de la secuencia y el formateador que piensa utilizar y, a continuación, llama al método **Serialize** en el formateador.La secuencia y el objeto para serializar se proporcionan como parámetros a esta llamada.Aunque no se muestra explícitamente en este ejemplo, todas las variables miembro de una clase serán serializadas, incluso las variables marcadas como privadas.En este aspecto, la serialización binaria difiere de la [Clase XMLSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx), que solo serializa los campos públicos.Para obtener información sobre cómo excluir las variables miembro de la serialización binaria, vea [la Serialización Selectiva](../../../docs/framework/serialization/selective-serialization.md).  
  
 Restaurar el objeto a su estado anterior es así de fácil.Primero, cree una secuencia para leer y un [formateador](frlrfSystemRuntimeSerializationFormatterClassTopic) y, a continuación, indica al formateador que deserialice el objeto.El ejemplo de código siguiente muestra cómo se realiza la acción.  
  
```csharp  
IFormatter formatter = new BinaryFormatter();  
Stream stream = new FileStream("MyFile.bin", FileMode.Open, FileAccess.Read, FileShare.Read);  
MyObject obj = (MyObject) formatter.Deserialize(stream);  
stream.Close();  
  
// Here's the proof.  
Console.WriteLine("n1: {0}", obj.n1);  
Console.WriteLine("n2: {0}", obj.n2);  
Console.WriteLine("str: {0}", obj.str);  
```  
  
 [BinaryFormatter](frlrfSystemRuntimeSerializationFormattersBinaryBinaryFormatterClassTopic) utilizado arriba es muy eficaz y genera una secuencia de bytes compacta.Todos los objetos serializados con este formateador también se pueden deserializar con él, que lo convierte en una herramienta ideal para serializar objetos que se deserializarán en .NET Framework.Es importante tener en cuenta que no se llama a los constructores cuando se deserializa un objeto.Esta restricción se coloca en deserialización por las razones de rendimiento.Sin embargo, esto infringe algunos de los contratos usuales hechos en tiempo de ejecución con la escritura de objeto y los programadores debería asegurarse que entienden las ramificaciones al marcar un objeto como serializable.  
  
 Si la portabilidad es un requisito, utilice en su lugar [SoapFormatter](frlrfSystemRuntimeSerializationFormattersSoapSoapFormatterClassTopic).Simplemente reemplace **BinaryFormatter** en el código anterior con **SoapFormatter** y llame a **Serializar** y **Deserializar** como antes.Este formateador genera el resultado siguiente para obtener el ejemplo utilizado anteriormente.  
  
```  
<SOAP-ENV:Envelope  
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
  xmlns:SOAP- ENC="http://schemas.xmlsoap.org/soap/encoding/"  
  xmlns:SOAP- ENV="http://schemas.xmlsoap.org/soap/envelope/"  
  SOAP-ENV:encodingStyle=  
  "http://schemas.microsoft.com/soap/encoding/clr/1.0"  
  "http://schemas.xmlsoap.org/soap/encoding/"  
  xmlns:a1="http://schemas.microsoft.com/clr/assem/ToFile">  
  
  <SOAP-ENV:Body>  
    <a1:MyObject id="ref-1">  
      <n1>1</n1>  
      <n2>24</n2>  
      <str id="ref-3">Some String</str>  
    </a1:MyObject>  
  </SOAP-ENV:Body>  
</SOAP-ENV:Envelope>  
```  
  
 Es importante tener en cuenta que el atributo **Serializable** no pueda estar heredado.Si deriva una nueva clase de `MyObject`, la nueva clase también se debe marcar con el atributo o no se puede serializar.Por ejemplo, al intentar serializar una instancia de la clase siguiente, obtendrá [SerializationException](frlrfSystemRuntimeSerializationSerializationExceptionClassTopic) que lo informa que el tipo `MyStuff` no se marca como serializable.  
  
```csharp  
public class MyStuff : MyObject   
{  
  public int n3;  
}  
```  
  
 Utilizar el atributo **Serializable** es conveniente, pero tiene las limitaciones como se ha mostrado anteriormente.Consulte las [Instrucciones de la Serialización](../../../docs/framework/serialization/serialization-guidelines.md) para obtener información sobre cuando se debe marcar una clase para la serialización; la serialización no se puede agregar a una clase una vez estado compilado.  
  
## Vea también  
 [Serialización binaria](../../../docs/framework/serialization/binary-serialization.md)   
 [Remote Objects](http://msdn.microsoft.com/es-es/515686e6-0a8d-42f7-8188-73abede57c58)   
 [Serialización de SOAP y XML](../../../docs/framework/serialization/xml-and-soap-serialization.md)