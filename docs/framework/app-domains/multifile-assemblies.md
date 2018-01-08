---
title: Ensamblados de varios archivos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- command-line compilers
- assembly manifest, multifile assemblies
- code modules
- multifile assemblies
ms.assetid: 13509e73-db77-4645-8165-aad8dfaedff6
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bded4fae854d10a17ddd03b8855f6096e18ab87f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="multifile-assemblies"></a>Ensamblados de varios archivos
Puede crear ensamblados de varios archivos mediante compiladores de línea de comandos o [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] con Visual C++. Un archivo del ensamblado debe contener el manifiesto del ensamblado. Los ensamblados que inicien una aplicación también deben contener un punto de entrada, como un método Main o WinMain.  
  
 Por ejemplo, supongamos que tiene una aplicación que contiene dos módulos de código, Client.cs y Stringer.cs. Stringer.cs que crea el espacio de nombres `myStringer` al que hace referencia el código de Client.cs. Client.cs contiene el método `Main`, que es el punto de entrada de la aplicación. En este ejemplo, se compilan los dos módulos de código y, después, se crea un tercer archivo que contiene el manifiesto del ensamblado, que inicia la aplicación. El manifiesto del ensamblado hace referencia a los módulos `Client` y `Stringer`.  
  
> [!NOTE]
>  Los ensamblados de varios archivos pueden tener un único punto de entrada, incluso si el ensamblado tiene varios módulos de código.  
  
 Hay varias razones por las que le puede interesar crear un ensamblado de varios archivos:  
  
-   Para combinar módulos escritos en lenguajes diferentes. Esta es la razón más común para crear un ensamblado de varios archivos.  
  
-   Para optimizar la descarga de una aplicación al colocar los tipos menos usados en un módulo que solo se descarga cuando es necesario.  
  
    > [!NOTE]
    >  Si va a crear aplicaciones que se descargarán mediante la etiqueta `<object>` con Microsoft Internet Explorer, es importante que cree ensamblados de varios archivos. En este escenario, debe crear un archivo independiente de los módulos de código que solo contenga el manifiesto del ensamblado. Internet Explorer descarga primero el manifiesto del ensamblado y, después, crea subprocesos de trabajo para descargar los módulos o ensamblados adicionales necesarios. Mientras se descarga el archivo que contiene el manifiesto del ensamblado, Internet Explorer no responde a la entrada del usuario. Cuanto menor sea el archivo que contiene el manifiesto del ensamblado, menos tiempo estará sin responder Internet Explorer.  
  
-   Para combinar módulos de código escritos por varios desarrolladores. Aunque cada desarrollador puede compilar cada módulo de código en un ensamblado, esto puede hacer que se expongan públicamente algunos tipos que no se exponen cuando todos los módulos se colocan en un ensamblado de varios archivos.  
  
 Una vez creado el ensamblado, puede firmar el archivo que contiene el manifiesto del ensamblado (y, por tanto, el ensamblado), o bien puede asignarle al archivo (y al ensamblado) un nombre seguro y colocarlo en la caché global de ensamblados.  
  
## <a name="see-also"></a>Vea también  
 [Compilar un ensamblado de varios archivos](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)  
 [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)
