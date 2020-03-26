---
title: Serialización básica
ms.date: 03/30/2017
helpviewer_keywords:
- binary serialization, basic serialization
- serialization, basic serialization
ms.assetid: d899d43c-335a-433e-a589-cd187192984f
dev_langs:
- CSharp
ms.openlocfilehash: ce86f7897c5c117c4fd6f1eabc4c8b802103261c
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80248035"
---
# <a name="basic-serialization"></a>Serialización básica

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

La manera más sencilla de convertir una clase en serializable es marcarla con <xref:System.SerializableAttribute> como se muestra a continuación.  
  
```csharp  
[Serializable]  
public class MyObject {  
  public int n1 = 0;  
  public int n2 = 0;  
  public String str = null;  
}  
```  
  
El ejemplo de código siguiente muestra cómo serializar una instancia de esta clase en un archivo.  
  
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
  
Este ejemplo utiliza un formateador binario para hacer la serialización. Todo lo que necesita hacer es crear una instancia del flujo y el formateador que piensa usar y luego llamar al método **Serialize** en el formateador. La secuencia y el objeto para serializar se proporcionan como parámetros a esta llamada. Aunque no se muestra explícitamente en este ejemplo, todas las variables miembro de una clase serán serializadas, incluso las variables marcadas como privadas. En este aspecto, la serialización binaria difiere de la clase <xref:System.Xml.Serialization.XmlSerializer>, que solo serializa campos públicos. Para más información sobre cómo excluir variables miembro de la serialización binaria, vea [Serialización selectiva](selective-serialization.md).  
  
Restaurar el objeto a su estado anterior es así de fácil. Primero, cree un flujo para leer y un <xref:System.Runtime.Serialization.Formatter> y luego indique al formateador que deserialice el objeto. El ejemplo de código siguiente muestra cómo se realiza la acción.  
  
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
  
El <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> usado arriba es muy eficaz y genera un flujo de bytes compacto. Todos los objetos serializados con este formateador también se pueden deserializar con él, que lo convierte en una herramienta ideal para serializar objetos que se deserializarán en .NET Framework. Es importante tener en cuenta que no se llama a los constructores cuando se deserializa un objeto. Esta restricción se coloca en deserialización por las razones de rendimiento. Sin embargo, esto infringe algunos de los contratos usuales hechos en tiempo de ejecución con la escritura de objeto y los programadores debería asegurarse que entienden las ramificaciones al marcar un objeto como serializable.  
  
Si la portabilidad es un requisito, use <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> en su lugar. Simplemente reemplace **BinaryFormatter** en el código anterior por **SoapFormatter** y llame a **Serialize** y **Deserialize** como antes. Este formateador genera el resultado siguiente para obtener el ejemplo utilizado anteriormente.  
  
```xml  
<SOAP-ENV:Envelope  
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"
  xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/"  
  xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"  
  SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/"  
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
  
Es importante tener en cuenta que el atributo [Serializable](xref:System.SerializableAttribute) no se puede heredar. Si deriva una nueva clase de `MyObject`, la nueva clase también se debe marcar con el atributo o no se puede serializar. Por ejemplo, al intentar serializar una instancia de la clase siguiente, se obtiene una <xref:System.Runtime.Serialization.SerializationException> que informa de que el tipo `MyStuff` no está marcado como serializable.  
  
```csharp  
public class MyStuff : MyObject
{  
  public int n3;  
}  
```  
  
 Es conveniente usar el atributo [Serializable](xref:System.SerializableAttribute), aunque tiene limitaciones, como se ha mostrado anteriormente. Vea [Directrices de serialización](serialization-guidelines.md) para más información sobre cuándo se debe marcar una clase para la serialización. La serialización no se puede agregar a una clase después de que se haya compilado.  
  
## <a name="see-also"></a>Vea también

- [Serialización binaria](binary-serialization.md)
- [Serialización de SOAP y XML](xml-and-soap-serialization.md)
