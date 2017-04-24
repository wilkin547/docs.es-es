---
title: "C&#243;mo: Especificar un enlace de cliente en la configuraci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4a7c79aa-50ee-4991-891e-adc0599323a7
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# C&#243;mo: Especificar un enlace de cliente en la configuraci&#243;n
En este ejemplo, se crea una aplicación de consola de cliente para utilizar un servicio de calculadora y el enlace para ese cliente se especifica de manera declarativa en la configuración. El cliente tiene acceso a la `CalculatorService`, que implementa el `ICalculator` interfaz y el servicio y el cliente utilizan el <xref:System.ServiceModel.BasicHttpBinding> clase.  
  
 El procedimiento descrito asume que el servicio de calculadora se está ejecutando. Para obtener información sobre cómo crear el servicio, consulte [Cómo: especificar un enlace de servicio en la configuración](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md). También usa el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) que [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] proporciona para generar automáticamente los componentes de cliente. La herramienta genera el código de cliente y la configuración para obtener acceso al servicio.  
  
 El cliente se crea en dos partes. Svcutil.exe genera la `ClientCalculator` que implementa la interfaz `ICalculator`. Esta aplicación de cliente se construye a continuación mediante la creación de una instancia de `ClientCalculator`.  
  
 Normalmente es el mejor procedimiento para especificar el enlace y la información de dirección de forma declarativa en configuración en lugar de hacerlo de forma imperativa en código. Normalmente, no resulta muy práctico definir los extremos en el código ya que los enlaces y las direcciones de un servicio implementado son, por lo general, diferentes de los utilizados durante el desarrollo del servicio. Más generalmente, manteniendo el enlace y la información de dirección fuera del código permite cambiarlos sin tener que recompilar o implementar la aplicación.  
  
 Puede realizar todos estos pasos de configuración mediante la [herramienta Editor de configuración (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
 Para la copia original de este ejemplo, consulte el [BasicBinding](../../../docs/framework/wcf/samples/basicbinding.md) ejemplo.  
  
### <a name="specifying-a-client-binding-in-configuration"></a>Especificación de un enlace de cliente mediante configuración  
  
1.  Utilice Svcutil.exe desde la línea de comandos para generar el código a partir de los metadatos del servicio.  
  
    ```  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
    ```  
  
2.  El cliente que se genera contiene la interfaz `ICalculator` que define el contrato de servicios que la implementación del cliente debe cumplir.  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#1)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#1)]  
  
3.  El cliente generado también contiene la implementación de `ClientCalculator`.  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#2)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#2)]  
  
4.  Svcutil.exe también genera la configuración del cliente que utiliza el <xref:System.ServiceModel.BasicHttpBinding> clase. Al utilizar [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], nombre a este archivo como App.config. Observe que la información de enlace y dirección no se especifican en ninguna parte de la implementación del servicio. Además, el código tiene que escribirse para recuperar esa información del archivo de configuración.  
  
     <!-- TODO: review snippet reference [!code[C_HowTo_ConfigureClientBinding#100](../../../samples/snippets/common/VS_Snippets_CFX/c_howto_configureclientbinding/common/client.exe.config#100)]  -->  
  
5.  Cree una instancia de `ClientCalculator` en una aplicación y, a continuación, llame a las operaciones del servicio.  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/client.cs#3)]  
  
6.  Compile y ejecute el cliente.  
  
## <a name="see-also"></a>Vea también  
 [Utilización de enlaces para configurar servicios y clientes](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)