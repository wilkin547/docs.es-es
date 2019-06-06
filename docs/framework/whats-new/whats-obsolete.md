---
title: Lo obsoleto en la biblioteca de clases de .NET Framework
ms.custom: updateeachrelease
ms.date: 04/02/2019
helpviewer_keywords:
- obsolete [.NET Framework]
- what's obsolete [.NET Framework]
- deprecated [.NET Framework]
ms.assetid: d356a43a-73df-4ae2-a457-b9628074c7cd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7db411e9ef38adb42c8df2059d166d1fa4184f95
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2019
ms.locfileid: "66378374"
---
# <a name="whats-obsolete-in-the-net-framework-class-library"></a>Lo obsoleto en la biblioteca de clases de .NET Framework

.NET Framework cambia con el tiempo. Cada nueva versión agrega nuevos tipos y miembros de tipos que proporcionan una nueva funcionalidad. Los tipos existentes y sus miembros también cambian con el tiempo. Por ejemplo, algunos tipos pierden importancia cuando la tecnología que admiten es reemplazada por una nueva y algunos métodos son sustituidos por métodos más nuevos que resultan más cómodos o están más completos.

.NET Framework y Common Language Runtime se esfuerzan por ser compatibles con versiones anteriores (permitir que aplicaciones que se desarrollaron con una versión de .NET Framework puedan ejecutarse en la versión siguiente de .NET Framework). Esto hace más difícil quitar simplemente un tipo o un miembro de tipo. En su lugar, .NET Framework indica que no se debería seguir utilizando un tipo o un miembro de tipo marcándolo como obsoleto o desusado. El desuso de un tipo o un miembro implica marcarlo para que los desarrolladores sean conscientes de que va a desaparecer y tengan tiempo para reaccionar antes de su eliminación. Sin embargo, el código existente que utiliza el tipo o el miembro continúa ejecutándose en la nueva versión de .NET Framework.

> [!NOTE]
> Los términos *obsoleto* y *en desuso* tienen el mismo significado cuando se aplican a los tipos y miembros de .NET Framework.

## <a name="the-obsoleteattribute-attribute"></a>El atributo ObsoleteAttribute

.NET Framework indica que un tipo o un miembro de tipo está obsoleto marcándolo con el atributo <xref:System.ObsoleteAttribute>. La aplicación del atributo a un tipo o miembro indica que ese tipo o miembro se quitará de alguna versión futura de .NET Framework sin interrumpir el código compilado que utiliza este miembro.

Además de indicar que un tipo o miembro de tipo está obsoleto, <xref:System.ObsoleteAttribute> define cómo administra el compilador el código fuente que incluye este tipo o miembro. El compilador puede compilar el código pero emitir un mensaje de advertencia o puede tratar el uso del tipo o miembro como un error. En el primer caso, el código puede compilarse correctamente, pero un mensaje de advertencia indica que el tipo o miembro está obsoleto. En el segundo caso, se produce un error de compilación.

Incluso si la compilación genera un error en lugar de un mensaje de advertencia, <xref:System.ObsoleteAttribute> no afecta al comportamiento en tiempo de ejecución. Es decir, las aplicaciones que utilizan el tipo o miembro y que se han compilado correctamente siempre se ejecutarán correctamente. Solo se produce un error en el intento de volver a compilar una aplicación que utiliza el tipo o miembro.

## <a name="how-to-handle-obsolete-types-and-members"></a>Cómo controlar los tipos y miembros obsoletos

Al actualizar y volver a compilar el código existente, el uso de un tipo o miembro obsoleto que genera una advertencia del compilador en su aplicación es absolutamente aceptable. Sin embargo, debería revisar el mensaje de advertencia del compilador para determinar si tiene que cambiar el código de aplicación. Si el mensaje no indica ninguna alternativa adecuada, debe realizar una de las siguientes operaciones:

- Cambie su código quitando el uso del tipo o miembro, si es posible.

     o bien

- Revise la documentación para que esta área de tecnología determine cómo responder al desuso.

Puede decidir no volver a compilar un código existente con una versión posterior de .NET Framework. En su lugar, puede especificar la versión de .NET Framework con la que se ejecuta el código compilado existente. Por ejemplo, supongamos que tiene una aplicación llamada app1.exe compilada con [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)], pero quiere que la aplicación se ejecute con .NET Framework 4.5. Para ello, siga estos pasos:

1. Cree un archivo de configuración para el ejecutable principal y denomínelo *appName*.exe.config, donde *appName* es el nombre del ejecutable de la aplicación. Para la aplicación denominada app1.exe en nuestro ejemplo, va a crear un archivo de configuración denominado app1.exe.config.

2. Agregue lo siguiente al archivo de configuración.

    ```xml
    <configuration>
       <startup> 
          <supportedRuntime version="v4.0" />
       </startup>
    </configuration>
    ```

En la siguiente tabla se muestra una lista de los valores de cadena que puede asignar al atributo `version` para destinarlo a una versión concreta de .NET Framework:

|Versión de .NET Framework|Cadena de `version`|
|-|-|
|4.8|v4.0|
|4.7 (incluidas 4.7.1 y 4.7.2)|v4.0|
|4.6 (incluidas 4.6.1 y 4.6.2)|v4.0|
|4.5 (incluidas 4.5.1 y 4.5.2)|v4.0|
|4|v4.0|
|3.5|v2.0.50727|
|2.0|v2.0.50727|
|1.1|v1.1.4322|
|1.0|v1.0.3705|

## <a name="obsolete-lists-for-the-net-framework-45-and-later-versions"></a>Listas de elementos obsoletos en .NET Framework 4.5 y versiones posteriores

- [Tipos obsoletos](obsolete-types.md)
- [Miembros obsoletos](obsolete-members.md)

## <a name="obsolete-lists-for-previous-versions"></a>Listas de elementos obsoletos en versiones anteriores

- [Tipos obsoletos en .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee461503(v=vs.100))

- [Miembros obsoletos en .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee471421(v=vs.100))

- [Lista de API obsoletas en .NET Framework 3.5](https://docs.microsoft.com/previous-versions/cc835481(v=msdn.10))

- [Lista de API obsoletas en .NET Framework 2.0](https://docs.microsoft.com/previous-versions/aa497286(v=msdn.10))

## <a name="see-also"></a>Vea también

- [\<supportedRuntime > Elemento](../configure-apps/file-schema/startup/supportedruntime-element.md)
