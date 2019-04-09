---
title: Filtrar para mejorar el tiempo de inicio de las aplicaciones cliente WCF mediante XmlSerializer
ms.date: 03/30/2017
ms.assetid: 21093451-0bc3-4b1a-9a9d-05f7f71fa7d0
ms.openlocfilehash: dfc3dc8247a25442511d422192fea4f49bee5d92
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169811"
---
# <a name="how-to-improve-the-startup-time-of-wcf-client-applications-using-the-xmlserializer"></a>Filtrar para mejorar el tiempo de inicio de las aplicaciones cliente WCF mediante XmlSerializer
Los servicios y las aplicaciones cliente que utilizan tipos de datos que son serializables utilizando <xref:System.Xml.Serialization.XmlSerializer> generan y compilan el código de la serialización para esos tipos de datos en el tiempo de ejecución, lo que se puede traducir en un rendimiento de inicio lento.  
  
> [!NOTE]
>  El código de serialización generado previamente solo puede usarse en aplicaciones cliente y no en servicios.  
  
 El [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) puede mejorar el rendimiento de inicio de estas aplicaciones generando el código de serialización necesarios desde los ensamblados compilados para la aplicación. Svcutil.exe genera el código de serialización para todos los tipos de datos utilizados en contratos de servicios en el ensamblado de aplicación de compilación que se puede serializar utilizando <xref:System.Xml.Serialization.XmlSerializer>. Los contratos de operación y servicio que utiliza el <xref:System.Xml.Serialization.XmlSerializer> se marcan con <xref:System.ServiceModel.XmlSerializerFormatAttribute>.  
  
### <a name="to-generate-xmlserializer-serialization-code"></a>Para generar el código de serialización de XmlSerializer  
  
1.  Compile su servicio o código de cliente en uno o más ensamblados.  
  
2.  Abra un símbolo del sistema de SDK.  
  
3.  En el símbolo del sistema, inicie la herramienta Svcutil.exe mediante el formato siguiente.  
  
    ```  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     El argumento `assemblyPath` especifica la ruta de acceso a un ensamblado que contiene tipos de contrato de servicio. Svcutil.exe genera el código de serialización para todos los tipos de datos utilizados en contratos de servicios en el ensamblado de aplicación de compilación que se puede serializar utilizando <xref:System.Xml.Serialization.XmlSerializer>.  
  
     Svcutil.exe solo puede generar código de serialización de C#. Un archivo de código fuente se genera para cada ensamblado de entrada. No puede usar el **/language** modificador para cambiar el lenguaje del código generado.  
  
     Para especificar la ruta de acceso a los ensamblados dependientes, use el **/reference** opción.  
  
4.  Haga que el código de serialización generado esté disponible para su aplicación utilizando una de las opciones siguientes:  
  
    1.  Compile el código de serialización generado en un ensamblado independiente con el nombre [*ensamblado original*]. .XmlSerializers.dll (por ejemplo, MyApp.XmlSerializers.dll). Su aplicación debe poder cargar el ensamblado, que se debe firmar con la misma clave como el ensamblado original. Si vuelve a compilar el ensamblado original, debe volver a generar el ensamblado de serialización.  
  
    2.  Compile el código de serialización generado en un ensamblado independiente y utilice <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> en el contrato de servicios que utiliza <xref:System.ServiceModel.XmlSerializerFormatAttribute>. Establezca las propiedades <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> o <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> para señalar al ensamblado de serialización compilado.  
  
    3.  Compile el código de serialización generado en su ensamblado de aplicación y agregue el <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> al contrato de servicios que utiliza el <xref:System.ServiceModel.XmlSerializerFormatAttribute>. No establezca las propiedades <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> ni <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A>. Se supone que el ensamblado de serialización predeterminado es el ensamblado actual.  
  
### <a name="to-generate-xmlserializer-serialization-code-in-visual-studio"></a>Para generar código de serialización de XmlSerializer en Visual Studio  
  
1.  Crear el servicio de WCF y el cliente los proyectos en Visual Studio. A continuación, agregue una referencia de servicio al proyecto de cliente.  
  
2.  Agregar un <xref:System.ServiceModel.XmlSerializerFormatAttribute> al contrato de servicio en la *reference.cs* archivo en el proyecto de aplicación de cliente en **serviceReference** -> **reference.svcmap** . Tenga en cuenta que deberá mostrar todos los archivos en **el Explorador de soluciones** para ver estos archivos.  
  
3.  Compile la aplicación cliente.  
  
4.  Use la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para crear un serializador previamente generado *.cs* archivo mediante el comando:  
  
    ```  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     El argumento assemblyPath especifica la ruta de acceso al ensamblado de cliente WCF.  
  
     Por ejemplo:  
  
    ```  
    svcutil.exe /t:xmlSerializer wcfclient.exe  
    ```  
  
     El *WCFClient.XmlSerializers.dll.cs* se generará el archivo.  
  
5.  Compile el ensamblado de serialización generado previamente.  
  
     Según el ejemplo en el paso anterior, el comando de compilación sería el siguiente:  
  
    ```  
    csc /r:wcfclient.exe /out:WCFClient.XmlSerializers.dll /t:library WCFClient.XmlSerializers.dll.cs  
    ```  
  
     Asegúrese de que la generada *WCFClient.XmlSerializers.dll* está en el mismo directorio que la aplicación cliente, que es *WCFClient.exe* en este caso.  
  
6.  Ejecute la aplicación cliente como de costumbre. Se usará el ensamblado de serialización generado previamente.  
  
## <a name="example"></a>Ejemplo  
 El siguiente comando genera los tipos de serialización para los tipos de `XmlSerializer` utilizados por cualquier contrato de servicios en el ensamblado.  
  
```  
svcutil /t:xmlserializer myContractLibrary.exe  
```  
  
## <a name="see-also"></a>Vea también

- [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
