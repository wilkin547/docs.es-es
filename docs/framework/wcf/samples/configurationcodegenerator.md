---
title: ConfigurationCodeGenerator
ms.date: 03/30/2017
ms.assetid: 3913aae8-165f-4014-9262-7fe426f90cb2
ms.openlocfilehash: 97197926db0b44f1ad36e2eba6ab6bec42eced33
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59773680"
---
# <a name="configurationcodegenerator"></a>ConfigurationCodeGenerator
ConfigurationCodeGenerator es una herramienta que puede utilizar para exponer sus implementaciones de canales personalizadas en el sistema de configuración. Esto permite a los usuarios de su canal personalizado configurar el canal utilizando un archivo .config tal y como lo haría si configuraran un enlace proporcionado por el sistema como `NetTcpBinding` o un enlace personalizado usando `TcpTransportBindingElement`.  
  
 Al escribir un canal personalizado y exponerlo en el modelo de programación usando un nuevo `BindingElement` o `Binding`, debe crear un conjunto de clases para convertir en configurable `BindingElement` o `Binding` utilizando un archivo .config. Puede utilizar la herramienta ConfigurationCodeGenerator para generar estas clases y mejorar la experiencia de su cliente.  
  
### <a name="to-build-the-tool"></a>Para compilar la herramienta  
  
1. Para compilar la solución, siga las instrucciones de [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2. Al compilar la solución, se genera un archivo: ConfigurationCodeGenerator.exe. ConfigurationCodeGenerator.exe. Samplerun.cmd del archivo tiene una línea de comandos de ejemplo que muestra cómo utilizar esta herramienta para generar las clases para el [transporte: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) ejemplo.  
  
### <a name="to-run-the-tool"></a>Para ejecutar la herramienta  
  
1. En el símbolo del sistema escriba lo siguiente si tiene un tipo `BindingElement` personalizado y un tipo `Binding` personalizado:  
  
    ```  
    ConfigurationCodeGenerator.exe /be:YourCustomBindingElementTypeName /sb:YourCustomStdBindingTypeName /dll:TheAssemblyWhereTheseTypesAreDefined  
    ```  
  
     O escriba lo siguiente si tiene sólo un tipo `BindingElement` personalizado:  
  
    ```  
    ConfigurationCodeGenerator.exe /be:YourCustomBindingElementTypeName /dll: TheAssemblyWhereThisTypeIsDefined  
    ```  
  
     O escriba lo siguiente si tiene sólo un tipo `Binding` personalizado:  
  
    ```  
    ConfigurationCodeGenerator.exe /sb:YourCustomStdBindingTypeName /dll:TheAssemblyWhereThisTypeIsDefined  
    ```  
  
     El comando genera tres archivos .cs para `BindingElement` (si especificó la opción /be), cinco archivos .cs para el `Binding` estándar (si especificó la opción /sb:) y un archivo .xml.  
  
    1.  Si utilizó la opción /be, uno de los archivos .cs implementa `BindingElementExtensionSection` para su elemento de enlace. Este código expone `BindingElement` en el sistema de configuración, para que otros enlaces personalizados puedan utilizar su elemento de enlace. Los otros archivos tienen clases que representan valores predeterminados y constantes. Los archivos tienen los comentarios `//TODO` para recordarle actualizar los valores predeterminados.  
  
    2.  Si especificó la opción /sb, dos de los archivos .cs implementan respectivamente `StandardBindingElement` y `StandardBindingCollectionElement`, que exponen el enlace estándar en el sistema de configuración. Los otros archivos tienen clases que representan valores predeterminados y constantes. Los archivos tienen los comentarios `//TODO` para recordarle actualizar los valores predeterminados.  
  
         Si especificó/SB: opción the CodeToAddTo\<*YourStdBinding*> .cs tiene código que se debe agregar manualmente a la clase que implementa su enlace estándar.  
  
     El archivo SampleConfig.xml contiene el código de configuración que debe agregar al archivo de configuración que registra los controladores definidos en el paso 1 o 2 anterior.  
