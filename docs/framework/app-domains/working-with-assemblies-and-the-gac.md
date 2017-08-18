---
title: "Trabajar con ensamblados y la memoria caché global de ensamblados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, benefits
- ACLs [.NET Framework]
- GAC (global assembly cache), benefits
- access control lists [.NET Framework]
ms.assetid: 8a18e5c2-d41d-49ef-abcb-7c27e2469433
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0c656cbad746e044a6dbf187ce86fd4738d6ef98
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="working-with-assemblies-and-the-global-assembly-cache"></a>Trabajar con ensamblados y la memoria caché global de ensamblados
Si se piensa compartir un ensamblado entre varias aplicaciones, puede instalarlo en la caché global de ensamblados. Cada equipo tiene esta memoria caché de código donde se instala Common Language Runtime. La caché global de ensamblados almacena los ensamblados designados específicamente para ser compartidos por varias aplicaciones del equipo. Un ensamblado debe tener un nombre seguro para que se pueda instalar en la caché global de ensamblados.  
  
> [!NOTE]
>  Los ensamblados ubicados en la caché global de ensamblados deben tener el mismo nombre de ensamblado y de archivo, sin contar la extensión de nombre de archivo. Por ejemplo, un ensamblado con el nombre de ensamblado myAssembly debe tener un nombre de archivo myAssembly.exe o myAssembly.dll.  
  
 Se recomienda compartir los ensamblados mediante su instalación en la caché global de ensamblados sólo cuando sea necesario. Como norma general, mantenga las dependencias de los ensamblados privadas y coloque los ensamblados en el directorio de la aplicación, a menos que sea necesario compartir un ensamblado en concreto. Además, no es necesario instalar los ensamblados en la caché global de ensamblados para que pueda tener acceso a ellos el código de interoperabilidad COM o el código no administrado.  
  
 Existen varias razones para instalar un ensamblado en la caché global de ensamblados:  
  
-   Ubicación compartida.  
  
     Los ensamblados que van a usar las aplicaciones se pueden poner en la caché global de ensamblados. Por ejemplo, si todas las aplicaciones deben usar un ensamblado ubicado en la caché global de ensamblados, se puede agregar una instrucción de directiva de versión al archivo Machine.config que redirige las referencias al ensamblado.  
  
-   Seguridad de archivos.  
  
     Con frecuencia, los administradores protegen el directorio systemroot con una Lista de control de acceso (ACL) para controlar el acceso de escritura y ejecución. Puesto que la caché global de ensamblados está instalada en el directorio systemroot, hereda la lista (ACL) de dicho directorio. Es recomendable que sólo puedan eliminar archivos de la caché global de ensamblados los usuarios que tengan privilegios de administrador.  
  
-   Control de versiones en paralelo.  
  
     En la caché global de ensamblados se pueden guardar muchas copias de ensamblados con el mismo nombre pero con distinta información de versión.  
  
-   Ubicación de búsqueda adicional.  
  
     Common Language Runtime busca en la caché global de ensamblados un ensamblado que coincida con la solicitud de ensamblado antes de buscar o utilizar la información de código base en un archivo de configuración.  
  
 Tenga en cuenta que hay escenarios en los que no deseará instalar un ensamblado en la memoria caché global de ensamblados. Si coloca uno de los ensamblados que componen una aplicación en la memoria caché global de ensamblados, ya no podrá replicar ni instalar la aplicación utilizando XCOPY para copiar el directorio de la aplicación. En este caso, debe mover también el ensamblado a la caché global de ensamblados.  
  
## <a name="in-this-section"></a>En esta sección  
 [Instalar un ensamblado en la memoria caché global de ensamblados](../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
 Describe las formas de instalar un ensamblado en la caché global de ensamblados.  
  
 [Consultar el contenido de la memoria caché global de ensamblados](../../../docs/framework/app-domains/how-to-view-the-contents-of-the-gac.md)  
 Explica cómo usar [Gacutil.exe (herramienta Caché global de ensamblados)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) para ver el contenido de la caché global de ensamblados.  
  
 [Quitar un ensamblado de la memoria caché global de ensamblados](../../../docs/framework/app-domains/how-to-remove-an-assembly-from-the-gac.md)  
 Explica cómo usar [Gacutil.exe (herramienta Caché global de ensamblados)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) para quitar un ensamblado de la caché global de ensamblados.  
  
 [Utilizar componentes con servicio junto con la memoria caché global de ensamblados](../../../docs/framework/app-domains/use-serviced-components-with-the-gac.md)  
 Explica por qué se deben colocar los componentes con servicio (componentes COM+ administrados) en la caché global de ensamblados.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Creación de ensamblados](../../../docs/framework/app-domains/create-assemblies.md)  
 Proporciona información general sobre la creación de ensamblados.  
  
 [Caché global de ensamblados](../../../docs/framework/app-domains/gac.md)  
 Describe la caché global de ensamblados.  
  
 [Ver el contenido de un ensamblado](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 Explica cómo usar [Ildasm.exe (Desensamblador de IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) para ver la información del Lenguaje intermedio de Microsoft (MSIL) de un ensamblado.  
  
 [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 Describe cómo Common Language Runtime busca y carga los ensamblados que conforman la aplicación.  
  
 [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 Describe los ensamblados, los bloques de creación de las aplicaciones administradas.

