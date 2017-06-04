---
title: "C&#243;mo: Especificar un enlace de servicio en la configuraci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 885037f7-1c2b-4d7a-90d9-06b89be172f2
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# C&#243;mo: Especificar un enlace de servicio en la configuraci&#243;n
En este ejemplo, se define un contrato `ICalculator` para un servicio de calculadora básico; el servicio se implementa en la clase `CalculatorService` y, después, su extremo se configura en el archivo Web.config, donde se especifica que el servicio usa <xref:System.ServiceModel.BasicHttpBinding>.Para una descripción de cómo configurar este servicio utilizando código en lugar de una configuración, vea [Cómo: Especificar un enlace de servicio en el código](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-code.md).  
  
 Normalmente es el mejor procedimiento para especificar el enlace y la información de dirección de forma declarativa en configuración en lugar de hacerlo de forma imperativa en código.Normalmente, no resulta muy práctico definir los extremos en el código ya que los enlaces y las direcciones de un servicio implementado son, por lo general, diferentes de los utilizados durante el desarrollo del servicio.Más generalmente, manteniendo el enlace y la información de dirección fuera del código permite cambiarlos sin tener que recompilar o implementar la aplicación.  
  
 Todos los pasos de configuración siguientes se pueden realizar utilizando [Herramienta del editor de configuración \(SvcConfigEditor.exe\)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
 Para la copia de origen de este ejemplo, vea [BasicBinding](../../../docs/framework/wcf/samples/basicbinding.md).  
  
### Para especificar BasicHttpBinding para utilizarlo para configurar el servicio  
  
1.  Defina un contrato de servicios para el tipo de servicio.  
  
     [!code-csharp[C_HowTo_ConfigureServiceBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureservicebinding/cs/source.cs#1)]
     [!code-vb[C_HowTo_ConfigureServiceBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_configureservicebinding/vb/source.vb#1)]  
  
2.  Implemente el contrato de servicios en una clase de servicio.  
  
     [!code-csharp[C_HowTo_ConfigureServiceBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureservicebinding/cs/source.cs#2)]
     [!code-vb[C_HowTo_ConfigureServiceBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_configureservicebinding/vb/source.vb#2)]  
  
    > [!NOTE]
    >  La información de dirección o enlace no se especifica dentro de la implementación del servicio.Por lo tanto, el código no tiene que escribirse para recuperar esa información del archivo de configuración.  
  
3.  Cree un archivo Web.config para configurar un extremo para `CalculatorService` que utiliza <xref:System.ServiceModel.WSHttpBinding>.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name=" CalculatorService" >  
            <endpoint   
            <-- Leave the address blank to be populated by default-->  
            <--from the hosting environment,in this case IIS, so -->  
            <-- the address will just be that of the IIS Virtual -->  
            <--Directory.-->  
                address=""   
            <--Specify the binding type -->  
                binding="wsHttpBinding"  
            <--Specify the binding configuration name for that -->  
            <--binding type. This is optional but useful if you  -->  
            <--want to modify the properties of the binding. -->  
            <--The bindingConfiguration name Binding1 is defined  -->  
            <--below in the bindings element.  -->  
                bindingConfiguration="Binding1"  
                contract="ICalculator" />  
          </service>  
        </services>  
        <bindings>  
          <wsHttpBinding>  
            <binding name="Binding1">  
              <-- Binding property values can be modified here. -->  
              <--See the next procedure. -->  
            </binding>  
          </wsHttpBinding>  
       </bindings>  
      </system.serviceModel>  
    </configuration>  
  
    ```  
  
4.  Cree un archivo Service.svc que contenga la línea siguiente y colóquelo en su directorio virtual de Internet Information Services \(IIS\).  
  
    ```  
    <%@ServiceHost language=c# Service="CalculatorService" %>   
    ```  
  
### Para modificar los valores predeterminados de las propiedades de enlace  
  
1.  Para modificar uno de los valores de propiedad predeterminados de <xref:System.ServiceModel.WSHttpBinding>, cree un nuevo nombre de la configuración de enlace \(`<binding name="Binding1">`[\<wsHttpBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) y establezca los nuevos valores para los atributos del enlace en este elemento de enlace.Por ejemplo, para cambiar los valores predeterminados de abrir y cerrar el tiempo de espera de 1 minuto a 2 minutos, agregue el siguiente al archivo de configuración.  
  
    ```  
    <wsHttpBinding>  
      <binding name="Binding1"  
               closeTimeout="00:02:00"  
               openTimeout="00:02:00">  
      </binding>  
    </wsHttpBinding>  
    ```  
  
## Vea también  
 [Utilización de enlaces para configurar servicios y clientes](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)   
 [Especificación de una dirección de extremo](../../../docs/framework/wcf/specifying-an-endpoint-address.md)