---
title: Trabajar con ensamblados y la memoria caché global de ensamblados
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, benefits
- ACLs [.NET Framework]
- GAC (global assembly cache), benefits
- access control lists [.NET Framework]
ms.assetid: 8a18e5c2-d41d-49ef-abcb-7c27e2469433
ms.openlocfilehash: 7834fbc4d74b44c4bc5204ac451e92cac22e1ef5
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645418"
---
# <a name="working-with-assemblies-and-the-global-assembly-cache"></a>Trabajar con ensamblados y la memoria caché global de ensamblados

Si se piensa compartir un ensamblado entre varias aplicaciones, puede instalarlo en la caché global de ensamblados. Cada equipo tiene esta memoria caché de código donde se instala Common Language Runtime. La caché global de ensamblados almacena los ensamblados designados específicamente para ser compartidos por varias aplicaciones del equipo. Un ensamblado debe tener un nombre seguro para que se pueda instalar en la caché global de ensamblados.  
  
> [!NOTE]
> Los ensamblados ubicados en la caché global de ensamblados deben tener el mismo nombre de ensamblado y de archivo, sin contar la extensión de nombre de archivo. Por ejemplo, un ensamblado con el nombre de ensamblado myAssembly debe tener un nombre de archivo myAssembly.exe o myAssembly.dll.  
  
Se recomienda compartir los ensamblados mediante su instalación en la caché global de ensamblados sólo cuando sea necesario. Como norma general, mantenga las dependencias de los ensamblados privadas y coloque los ensamblados en el directorio de la aplicación, a menos que sea necesario compartir un ensamblado en concreto. Además, no es necesario instalar los ensamblados en la caché global de ensamblados para que pueda tener acceso a ellos el código de interoperabilidad COM o el código no administrado.  
  
Existen varias razones para instalar un ensamblado en la caché global de ensamblados:  
  
- Ubicación compartida.  
  
     Los ensamblados que van a usar las aplicaciones se pueden poner en la caché global de ensamblados. Por ejemplo, si todas las aplicaciones deben usar un ensamblado ubicado en la caché global de ensamblados, se puede agregar una instrucción de directiva de versión al archivo Machine.config que redirige las referencias al ensamblado.  
  
- Seguridad de archivos.  
  
     Con frecuencia, los administradores protegen el directorio systemroot con una Lista de control de acceso (ACL) para controlar el acceso de escritura y ejecución. Puesto que la caché global de ensamblados está instalada en el directorio systemroot, hereda la lista (ACL) de dicho directorio. Es recomendable que sólo puedan eliminar archivos de la caché global de ensamblados los usuarios que tengan privilegios de administrador.  
  
- Control de versiones en paralelo.  
  
     En la caché global de ensamblados se pueden guardar muchas copias de ensamblados con el mismo nombre pero con distinta información de versión.  
  
- Ubicación de búsqueda adicional.  
  
     Common Language Runtime busca en la caché global de ensamblados un ensamblado que coincida con la solicitud de ensamblado antes de buscar o utilizar la información de código base en un archivo de configuración.  
  
 Tenga en cuenta que hay escenarios en los que no deseará instalar un ensamblado en la memoria caché global de ensamblados. Si coloca uno de los ensamblados que componen una aplicación en la memoria caché global de ensamblados, ya no podrá replicar ni instalar la aplicación utilizando XCOPY para copiar el directorio de la aplicación. En este caso, debe mover también el ensamblado a la caché global de ensamblados.  
  
## <a name="in-this-section"></a>En esta sección  
[Cómo: Instalar un ensamblado en la caché global de ensamblados](install-assembly-into-gac.md)  
Describe las formas de instalar un ensamblado en la caché global de ensamblados.  
  
[Cómo: Consultar el contenido de la memoria caché global de ensamblados](how-to-view-the-contents-of-the-gac.md)  
Explica cómo usar [Gacutil.exe (herramienta Caché global de ensamblados)](../tools/gacutil-exe-gac-tool.md) para ver el contenido de la caché global de ensamblados.  
  
[Cómo: Quitar un ensamblado de la memoria caché global de ensamblados](how-to-remove-an-assembly-from-the-gac.md)  
Explica cómo usar [Gacutil.exe (herramienta Caché global de ensamblados)](../tools/gacutil-exe-gac-tool.md) para quitar un ensamblado de la caché global de ensamblados.  
  
[Utilizar componentes con servicio junto con la memoria caché global de ensamblados](use-serviced-components-with-the-gac.md)  
Explica por qué se deben colocar los componentes con servicio (componentes COM+ administrados) en la caché global de ensamblados.  
  
## <a name="related-sections"></a>Secciones relacionadas  

[Creación de ensamblados](../../standard/assembly/create.md)  
Proporciona información general sobre la creación de ensamblados.  
  
[Caché global de ensamblados](gac.md)  
Describe la caché global de ensamblados.  
  
[Cómo: Ver el contenido de un ensamblado](../../standard/assembly/view-contents.md)  
Explica cómo usar [Ildasm.exe (Desensamblador de IL)](../tools/ildasm-exe-il-disassembler.md) para ver la información del Lenguaje intermedio de Microsoft (MSIL) de un ensamblado.  
  
[Cómo el motor en tiempo de ejecución ubica ensamblados](../deployment/how-the-runtime-locates-assemblies.md)  
Describe cómo Common Language Runtime busca y carga los ensamblados que conforman la aplicación.  
  
[Programar con ensamblados](../../standard/assembly/index.md)  
Describe los ensamblados, los bloques de creación de las aplicaciones administradas.
