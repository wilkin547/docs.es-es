---
title: Procedimiento para mejorar el tiempo de inicio de las aplicaciones cliente WCF mediante XmlSerializer
ms.date: 03/30/2017
ms.assetid: 21093451-0bc3-4b1a-9a9d-05f7f71fa7d0
ms.openlocfilehash: ac54a766161db146331a3e072b97822b609344c0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96246386"
---
# <a name="how-to-improve-the-startup-time-of-wcf-client-applications-using-the-xmlserializer"></a>Procedimiento para mejorar el tiempo de inicio de las aplicaciones cliente WCF mediante XmlSerializer

Los servicios y las aplicaciones cliente que utilizan tipos de datos que son serializables utilizando <xref:System.Xml.Serialization.XmlSerializer> generan y compilan el código de la serialización para esos tipos de datos en el tiempo de ejecución, lo que se puede traducir en un rendimiento de inicio lento.  
  
> [!NOTE]
> El código de serialización generado previamente solo puede usarse en aplicaciones cliente y no en servicios.  
  
 La [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) puede mejorar el rendimiento de inicio de estas aplicaciones mediante la generación del código de serialización necesario a partir de los ensamblados compilados para la aplicación. Svcutil.exe genera el código de serialización para todos los tipos de datos utilizados en contratos de servicios en el ensamblado de aplicación de compilación que se puede serializar utilizando <xref:System.Xml.Serialization.XmlSerializer>. Los contratos de operación y servicio que utiliza el <xref:System.Xml.Serialization.XmlSerializer> se marcan con <xref:System.ServiceModel.XmlSerializerFormatAttribute>.  
  
### <a name="to-generate-xmlserializer-serialization-code"></a>Para generar el código de serialización de XmlSerializer  
  
1. Compile su servicio o código de cliente en uno o más ensamblados.  
  
2. Abra un símbolo del sistema de SDK.  
  
3. En el símbolo del sistema, inicie la herramienta Svcutil.exe mediante el formato siguiente.  
  
    ```console  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     El argumento `assemblyPath` especifica la ruta de acceso a un ensamblado que contiene tipos de contrato de servicio. Svcutil.exe genera el código de serialización para todos los tipos de datos utilizados en contratos de servicios en el ensamblado de aplicación de compilación que se puede serializar utilizando <xref:System.Xml.Serialization.XmlSerializer>.  
  
     Svcutil.exe solo puede generar código de serialización de C#. Un archivo de código fuente se genera para cada ensamblado de entrada. No se puede usar el modificador **/Language** para cambiar el lenguaje del código generado.  
  
     Para especificar la ruta de acceso a los ensamblados dependientes, use la opción **/Reference** .  
  
4. Haga que el código de serialización generado esté disponible para su aplicación utilizando una de las opciones siguientes:  
  
    1. Compile el código de serialización generado en un ensamblado independiente con el nombre [*ensamblado original*] .XmlSerializers.dll (por ejemplo, MyApp.XmlSerializers.dll). Su aplicación debe poder cargar el ensamblado, que se debe firmar con la misma clave como el ensamblado original. Si vuelve a compilar el ensamblado original, debe volver a generar el ensamblado de serialización.  
  
    2. Compile el código de serialización generado en un ensamblado independiente y utilice <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> en el contrato de servicios que utiliza <xref:System.ServiceModel.XmlSerializerFormatAttribute>. Establezca las propiedades <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> o <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> para señalar al ensamblado de serialización compilado.  
  
    3. Compile el código de serialización generado en su ensamblado de aplicación y agregue el <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> al contrato de servicios que utiliza el <xref:System.ServiceModel.XmlSerializerFormatAttribute>. No establezca las propiedades <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> ni <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A>. Se supone que el ensamblado de serialización predeterminado es el ensamblado actual.  
  
### <a name="to-generate-xmlserializer-serialization-code-in-visual-studio"></a>Para generar código de serialización XmlSerializer en Visual Studio  
  
1. Cree los proyectos de servicio y cliente de WCF en Visual Studio. A continuación, agregue una referencia de servicio al proyecto de cliente.  
  
2. Agregue un <xref:System.ServiceModel.XmlSerializerFormatAttribute> al contrato de servicio en el archivo *Reference.CS* en el proyecto de la aplicación cliente en **serviceReference**  ->  **Reference. svcmap**. Tenga en cuenta que tiene que Mostrar todos los archivos de **Explorador de soluciones** para ver estos archivos.  
  
3. Compile la aplicación cliente.  
  
4. Use la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) para crear un archivo *. CS* de serializador generado previamente mediante el comando:  
  
    ```console  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     El argumento assemblyPath especifica la ruta de acceso al ensamblado de cliente de WCF.  
  
     Como:  
  
    ```console  
    svcutil.exe /t:xmlSerializer wcfclient.exe  
    ```  
  
     Se generará el archivo *WCFClient.XmlSerializers.dll. CS* .  
  
5. Compile el ensamblado de serialización generado previamente.  
  
     Según el ejemplo del paso anterior, el comando de compilación sería el siguiente:  
  
    ```console  
    csc /r:wcfclient.exe /out:WCFClient.XmlSerializers.dll /t:library WCFClient.XmlSerializers.dll.cs  
    ```  
  
     Asegúrese de que el *WCFClient.XmlSerializers.dll* generado se encuentra en el mismo directorio que la aplicación cliente, que se *WCFClient.exe* en este caso.  
  
6. Ejecute la aplicación cliente como de costumbre. Se utilizará el ensamblado de serialización generado previamente.  
  
## <a name="example"></a>Ejemplo  

 El siguiente comando genera los tipos de serialización para los tipos de `XmlSerializer` utilizados por cualquier contrato de servicios en el ensamblado.  
  
```console  
svcutil /t:xmlserializer myContractLibrary.exe  
```  
  
## <a name="see-also"></a>Vea también

- [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
