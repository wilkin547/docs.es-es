---
title: Lo obsoleto en la biblioteca de clases .NET Framework
ms.custom: updateeachrelease
ms.date: 10/17/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords:
- obsolete [.NET Framework]
- what's obsolete [.NET Framework]
- deprecated [.NET Framework]
ms.assetid: d356a43a-73df-4ae2-a457-b9628074c7cd
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d5fc41473c4a3ea812013ee7e5204c22d0a694d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="what39s-obsolete-in-the-net-framework-class-library"></a>Lo obsoleto en la biblioteca de clases .NET Framework
.NET Framework cambia con el tiempo. Cada nueva versión agrega nuevos tipos y miembros de tipos que proporcionan una nueva funcionalidad. Los tipos existentes y sus miembros también cambian con el tiempo. Por ejemplo, algunos tipos pierden importancia cuando la tecnología que admiten es reemplazada por una nueva y algunos métodos son sustituidos por métodos más nuevos que resultan más cómodos o están más completos.  
  
 .NET Framework y Common Language Runtime se esfuerzan por ser compatibles con versiones anteriores (permitir que aplicaciones que se desarrollaron con una versión de .NET Framework puedan ejecutarse en la versión siguiente de .NET Framework). Esto hace más difícil quitar simplemente un tipo o un miembro de tipo. En su lugar, .NET Framework indica que no se debería seguir utilizando un tipo o un miembro de tipo marcándolo como obsoleto o desusado. El desuso de un tipo o un miembro implica marcarlo para que los desarrolladores sean conscientes de que va a desaparecer y tengan tiempo para reaccionar antes de su eliminación. Sin embargo, el código existente que utiliza el tipo o el miembro continúa ejecutándose en la nueva versión de .NET Framework.  
  
> [!NOTE]
>  Los términos *obsoleto* y *en desuso* tienen el mismo significado cuando se aplican a los tipos y miembros de .NET Framework.  
  
## <a name="the-obsoleteattribute-attribute"></a>El atributo ObsoleteAttribute  
 .NET Framework indica que un tipo o un miembro de tipo está obsoleto marcándolo con el atributo <xref:System.ObsoleteAttribute>. La aplicación del atributo a un tipo o miembro indica que ese tipo o miembro se quitará de alguna versión futura de .NET Framework sin interrumpir el código compilado que utiliza este miembro.  
  
 Además de indicar que un tipo o miembro de tipo está obsoleto, <xref:System.ObsoleteAttribute> define cómo administra el compilador el código fuente que incluye este tipo o miembro. El compilador puede compilar el código pero emitir un mensaje de advertencia o puede tratar el uso del tipo o miembro como un error. En el primer caso, el código puede compilarse correctamente, pero un mensaje de advertencia indica que el tipo o miembro está obsoleto. En el segundo caso, se produce un error de compilación.  
  
 Incluso si la compilación genera un error en lugar de un mensaje de advertencia, <xref:System.ObsoleteAttribute> no afecta al comportamiento en tiempo de ejecución. Es decir, las aplicaciones que utilizan el tipo o miembro y que se han compilado correctamente siempre se ejecutarán correctamente. Solo se produce un error en el intento de volver a compilar una aplicación que utiliza el tipo o miembro.  
  
## <a name="how-to-handle-obsolete-types-and-members"></a>Cómo administrar tipos y miembros obsoletos  
 Al actualizar y volver a compilar el código existente, el uso de un tipo o miembro obsoleto que genera una advertencia del compilador en su aplicación es absolutamente aceptable. Sin embargo, debería revisar el mensaje de advertencia del compilador para determinar si tiene que cambiar el código de aplicación. Si el mensaje no indica ninguna alternativa adecuada, debe realizar una de las siguientes operaciones:  
  
-   Cambie su código quitando el uso del tipo o miembro, si es posible.  
  
     O bien  
  
-   Revise la documentación para que esta área de tecnología determine cómo responder al desuso.  
  
 Puede decidir no volver a compilar un código existente con una versión posterior de .NET Framework. En su lugar, puede especificar la versión de .NET Framework con la que se ejecuta el código compilado existente. Por ejemplo, suponga que tiene una aplicación denominada app1.exe que se compiló con [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)], pero desea que la aplicación se ejecute con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]. Para ello, siga estos pasos:  
  
1.  Cree un archivo de configuración para el ejecutable principal y denomínelo *appName*.exe.config, donde *appName* es el nombre del ejecutable de la aplicación. Para la aplicación denominada app1.exe en nuestro ejemplo, va a crear un archivo de configuración denominado app1.exe.config.  
  
2.  Agregue lo siguiente al archivo de configuración.  
  
    ```xml  
    <configuration>  
       <startup>   
          <supportedRuntime version="v4.0" />  
       </startup>  
    </configuration>  
    ```  
  
 En la siguiente tabla se muestra una lista de los valores de cadena que puede asignar al atributo `version` para una versión concreta de .NET Framework.  
  
|Versión de .NET Framework|Cadena de `version`|
|-|-|  
|4.7 (incluida 4.7.1)|v4.0|  
|4.6 (incluidas 4.6.1 y 4.6.2)|v4.0|  
|4.5 (incluidas 4.5.1 y 4.5.2)|v4.0|  
|4|v4.0|  
|3.5|v2.0.50727|  
|2.0|v2.0.50727|  
|1.1|v1.1.4322|  
|1.0|v1.0.3705|  
  
## <a name="obsolete-lists-for-the-net-framework-45-and-46"></a>Listas obsoletas para .NET Framework 4.5 y 4.6  
 [Tipos obsoletos](../../../docs/framework/whats-new/obsolete-types.md)  
  
 [Miembros obsoletos](../../../docs/framework/whats-new/obsolete-members.md)  
  
## <a name="obsolete-lists-for-previous-versions"></a>Listas de obsoletos para versiones anteriores  
 [Tipos obsoletos en .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=224224)  
  
 [Miembros obsoletos en .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=224227)  
  
 [Lista de API obsoletas en .NET Framework 3.5](http://go.microsoft.com/fwlink/?LinkId=163710)  
  
 [Lista de API obsoletas en .NET Framework 2.0](http://go.microsoft.com/fwlink/?LinkID=125264)  
  
## <a name="see-also"></a>Vea también  
 [\<supportedRuntime > Elemento](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)
