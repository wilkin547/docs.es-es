---
title: "Ejemplo de tecnolog&#237;a de serializaci&#243;n b&#225;sica | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9d824e16-08d1-4a36-bc7f-2388c1f75f34
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Ejemplo de tecnolog&#237;a de serializaci&#243;n b&#225;sica
[Descargar ejemplo](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Runtime%20Serialization/Basic.zip.exe)  
  
 En este ejemplo se demuestra la capacidad de Common Language Runtime para serializar un gráfico de objetos de la memoria en una secuencia.En este ejemplo se puede utilizar <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> o <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> para la serialización.Se serializa o deserializa una lista vinculada, llena de datos, desde o hacia una secuencia del archivo.En cualquier caso, se muestra la lista para que pueda ver los resultados.La lista vinculada es de tipo `LinkedList`, un tipo definido por este ejemplo.  
  
 Para obtener más información sobre la serialización, revise los comentarios de los archivos de código fuente y de build.proj.  
  
### Para generar el ejemplo desde el símbolo del sistema  
  
1.  Navegue hasta uno de los subdirectorios específicos de lenguaje bajo el directorio Technologies\\Serialization\\Runtime Serialization\\Basic, utilizando el símbolo del sistema.  
  
2.  Escriba **msbuild SerializationCS.sln**, **msbuild SerializationJSL.sln** o **msbuild SerializationVB.sln**, dependiendo del lenguaje de programación elegido, en la línea de comandos.  
  
### Para compilar el ejemplo mediante Visual Studio  
  
1.  Abra el [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] y navegue hasta uno de los subdirectorios específicos del lenguaje del ejemplo.  
  
2.  Haga doble clic en el icono del archivo SerializationCS.sln, SerializationJSL.sln o SerializationVB.sln, dependiendo del lenguaje de programación elegido, para abrir el archivo en Visual Studio.  
  
3.  En el menú **Compilar**, seleccione **Compilar solución**.  
  
 La aplicación de ejemplo se generará en el subdirectorio predeterminado \\bin o \\bin\\Debug.  
  
### Para ejecutar el ejemplo  
  
1.  Navegue hasta el directorio que contiene el ejecutable generado.  
  
2.  Escriba **Serialization.exe**, junto con los valores de parámetro que desee, en la línea de comandos.  
  
    > [!NOTE]
    >  En este ejemplo se genera una aplicación de consola.Para poder ver el resultado, debe iniciarla desde la línea de comandos.  
  
## Comentarios  
 La aplicación de ejemplo acepta parámetros de línea de comandos que indican qué comprobación desea ejecutar.Para serializar una lista de 10 nodos a un archivo denominado **Test.xml** mediante el formateador SOAP, utilice los parámetros **sx Test.xml 10**.  
  
 Por ejemplo:  
  
 **Serialize.exe \- sx Test.xml 10**  
  
 Para deserializar el archivo **Test.xml** del ejemplo anterior, utilice los parámetros **dx Test.xml**.  
  
 Por ejemplo:  
  
 **Serialize.exe \- dx Test.xml**  
  
 En los dos ejemplos anteriores, la "x" en el modificador de la línea de comandos indica que desea realizar una serialización de XML SOAP.Puede utilizar "b" en su lugar para utilizar la serialización binaria.Si desea realizar la serialización con un gran número de nodos, puede que prefiera redirigir el resultado de la consola a un archivo.  
  
 Por ejemplo:  
  
 **Serialize.exe \-sb Test.bin 10000 \>somefile.txt**  
  
 Las viñetas siguientes describen brevemente las clases y las tecnologías que se utilizan en este ejemplo.  
  
-   Serialización en tiempo de ejecución  
  
    -   <xref:System.Runtime.Serialization.IFormatter> Se utiliza para hacer referencia a un objeto <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> o <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>.  
  
    -   <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> Se utiliza para serializar una lista vinculada a una secuencia en formato binario.El formateador binario utiliza un formato que solo entiende el tipo <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.Sin embargo, los datos son concisos.  
  
    -   <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> Se utiliza para serializar una lista vinculada a una secuencia en formato SOAP.SOAP es un formato estándar.  
  
-   E\/S de secuencia  
  
    -   <xref:System.IO.Stream> Se utiliza para serializar y deserializar.El tipo de secuencia concreto utilizado en este ejemplo es el tipo <xref:System.IO.FileStream>.Sin embargo, la serialización se puede utilizar con cualquier tipo derivado de <xref:System.IO.Stream>.  
  
    -   <xref:System.IO.File> Se utiliza para crear objetos <xref:System.IO.FileStream> para leer y crear archivos en disco.  
  
    -   <xref:System.IO.FileStream> Se utiliza para serializar y deserializar las listas vinculadas.  
  
## Vea también  
 [Clase BinaryFormatter](frlrfSystemRuntimeSerializationFormattersBinaryBinaryFormatterClassTopic)   
 [Clase File](frlrfSystemIOFileClassTopic)   
 [Clase FileStream](frlrfSystemIOFileStreamClassTopic)   
 [Interfaz IFormatter](frlrfSystemRuntimeSerializationIFormatterClassTopic)   
 [Clase Random](https://msdn.microsoft.com/en-us/library/system.random.aspx)   
 [Atributo SerializableAttribute](frlrfSystemSerializableAttributeClassTopic)   
 [Clase SoapFormatter](frlrfSystemRuntimeSerializationFormattersSoapSoapFormatterClassTopic)   
 [Clase Stream](frlrfSystemIOStreamClassTopic)   
 [System.IO \(Espacio de nombres](https://msdn.microsoft.com/en-us/library/system.io.aspx)   
 [Espacio de nombres System.Runtime.Serialization](frlrfSystemRuntimeSerialization)   
 [Espacio de nombres System.Xml.Serialization](frlrfSystemXmlSerialization)   
 [Serialización básica](../../../docs/framework/serialization/basic-serialization.md)   
 [Serialización binaria](../../../docs/framework/serialization/binary-serialization.md)   
 [Controlar la serialización XML mediante atributos](../../../docs/framework/serialization/controlling-xml-serialization-using-attributes.md)   
 [Introducir la serialización XML](../../../docs/framework/serialization/introducing-xml-serialization.md)   
 [Serialización](../../../docs/framework/serialization/index.md)   
 [SOAP Service](http://msdn.microsoft.com/es-es/2051c992-28d1-499e-961f-17e9b675cec9)   
 [Serialización de SOAP y XML](../../../docs/framework/serialization/xml-and-soap-serialization.md)