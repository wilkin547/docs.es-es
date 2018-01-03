---
title: "Cómo: Crear contenedores COM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM,wrappers creating
- COM,wrappers Visual Studio
ms.assetid: bdf89bea-1623-45ee-a57b-cf7c90395efa
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 646c7fc6a8ebbb68f210637086db0e968e3533c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-com-wrappers"></a>Cómo: Crear contenedores COM
Puede crear contenedores del Modelo de objetos componentes (COM) mediante características de [!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)] o las herramientas Tlbimp.exe y Regasm.exe de .NET Framework. Ambos métodos generan dos tipos de contenedores COM:  
  
-   Un [contenedor RCW](../../../docs/framework/interop/runtime-callable-wrapper.md) desde una biblioteca de tipos para ejecutar un objeto COM en código administrado.  
  
-   Un [contenedor CCW](../../../docs/framework/interop/com-callable-wrapper.md) con la configuración del Registro necesaria para ejecutar un objeto administrado en una aplicación nativa.  
  
 En [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], puede agregar el contenedor COM como una referencia al proyecto.  
  
## <a name="wrapping-com-objects-in-a-managed-application"></a>Encapsulación de objetos COM en una aplicación administrada  
  
#### <a name="to-create-a-runtime-callable-wrapper-using-visual-studio"></a>Para crear un contenedor RCW con Visual Studio  
  
1.  Abra el proyecto de la aplicación administrada.  
  
2.  En el menú **Proyecto**, haga clic en **Mostrar todos los archivos**.  
  
3.  En el menú **Proyecto**, haga clic en **Agregar referencia**.  
  
4.  En el cuadro de diálogo Agregar referencia, haga clic en la pestaña **COM**, seleccione el componente que quiera usar y haga clic en **Aceptar**.  
  
     En el **Explorador de soluciones**, tenga en cuenta que el componente COM se agrega a la carpeta Referencias del proyecto.  
  
 Ahora puede escribir código para tener acceso al objeto COM. Puede comenzar declarando el objeto, por ejemplo con una instrucción `Imports` para [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] o una instrucción `Using` para [!INCLUDE[csprcslong](../../../includes/csprcslong-md.md)].  
  
> [!NOTE]
>  Si quiere programar componentes de Microsoft Office, instale primero los [ensamblados de interoperabilidad primarios de Microsoft Office](http://go.microsoft.com/fwlink/?LinkId=50479) (PIA) desde el Centro de descarga de Microsoft. En el paso 4, seleccione la versión más reciente de la biblioteca de objetos disponible para el producto de Office que quiere, como la **biblioteca de objetos de Microsoft Word 11.0**.  
  
#### <a name="to-create-a-runtime-callable-wrapper-using-net-framework-tools"></a>Para crear un contenedor RCW mediante las herramientas de .NET Framework  
  
-   Ejecute la herramienta [TlbImp.exe (Importador de la biblioteca de tipos)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md).  
  
 Esta herramienta crea un ensamblado que contiene los metadatos de tiempo de ejecución para los tipos definidos en la biblioteca de tipos original.  
  
## <a name="wrapping-managed-objects-in-a-native-application"></a>Encapsular objetos administrados en una aplicación nativa  
  
#### <a name="to-create-a-com-callable-wrapper-using-visual-studio"></a>Para crear un contenedor CCW con Visual Studio  
  
1.  Cree un proyecto de biblioteca de clases para la clase administrada que quiera ejecutar en código nativo. La clase debe tener un constructor predeterminado.  
  
     Compruebe que dispone de un número de versión de cuatro partes completo para el ensamblado en el archivo AssemblyInfo. Este número es necesario para mantener el control de versiones en el Registro de Windows. Para más información sobre los números de versión, vea [Versiones de los ensamblados](../../../docs/framework/app-domains/assembly-versioning.md).  
  
2.  En el menú **Proyecto**, haga clic en **Propiedades**.  
  
3.  Haga clic en la pestaña **Compilar**.  
  
4.  Active la casilla **Registrar para interoperabilidad COM**.  
  
 Al compilar el proyecto, el ensamblado se registra automáticamente para la interoperabilidad COM. Si va a compilar una aplicación nativa en [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], puede usar el ensamblado haciendo clic en **Agregar referencia** en el menú **Proyecto**.  
  
#### <a name="to-create-a-com-callable-wrapper-using-net-framework-tools"></a>Para crear un contenedor CCW mediante las herramientas de .NET Framework  
  
-   Ejecute la herramienta [Regasm.exe (Herramienta de registro de ensamblados)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md).  
  
 Esta herramienta lee los metadatos de ensamblado y agrega las entradas necesarias al Registro. Como resultado, los clientes COM pueden crear clases de .NET Framework de forma transparente. Puede usar el ensamblado como si fuera una clase COM nativa.  
  
 Puede ejecutar Regasm.exe en un ensamblado que se encuentre en cualquier directorio y, después, ejecutar [Gacutil.exe (herramienta de la caché global de ensamblados)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) para moverlo a la caché global de ensamblados. Al mover el ensamblado no se invalidan las entradas del registro de ubicación, porque siempre se examina la caché global de ensamblados si el ensamblado no se encuentra en otra parte.  
  
## <a name="see-also"></a>Vea también  
 [Contenedor al que se puede llamar en tiempo de ejecución](../../../docs/framework/interop/runtime-callable-wrapper.md)  
 [Contenedor CCW (COM callable wrapper)](../../../docs/framework/interop/com-callable-wrapper.md)
