---
title: Caché global de ensamblados
description: Obtenga información sobre la caché global de ensamblados. Se trata de una caché de código donde está instalado Common Language Runtime para .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- GAC (global assembly cache)
- ACLs [.NET Framework]
- global assembly cache
- cache [.NET Framework], global assembly cache
- global assembly cache, about
- access control lists [.NET Framework]
ms.assetid: cf5eacd0-d3ec-4879-b6da-5fd5e4372202
ms.openlocfilehash: 7f08bb4cf279924b12432f259dae8ce5a8474285
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104907"
---
# <a name="global-assembly-cache"></a>Caché global de ensamblados
Cada equipo donde está instalado Common Language Runtime tiene una memoria caché de código denominada caché global de ensamblados. La caché global de ensamblados almacena los ensamblados designados específicamente para ser compartidos por varias aplicaciones del equipo.  
  
 Se recomienda compartir los ensamblados mediante su instalación en la caché global de ensamblados solo cuando sea necesario. Como norma general, mantenga las dependencias de los ensamblados privadas y coloque los ensamblados en el directorio de la aplicación, a menos que sea explícitamente necesario compartir un ensamblado en concreto. Además, no es necesario instalar los ensamblados en la caché global de ensamblados para que el código de interoperabilidad COM o el código no administrado puedan acceder a ellos.  
  
> [!NOTE]
> Hay algunos escenarios en los que no se quiere instalar explícitamente un ensamblado en la caché global de ensamblados. Si coloca uno de los ensamblados que forman una aplicación en la caché global de ensamblados, ya no puede replicar ni instalar la aplicación mediante el comando **xcopy** para copiar su directorio. Además debe mover el ensamblado en la caché global de ensamblados.  
  
 Existen dos formas de implementar un ensamblado en la caché global de ensamblados:  
  
- Usar un instalador diseñado para funcionar con la caché global de ensamblados. Es la opción preferida para instalar ensamblados en la caché global de ensamblados.  
  
- Use la herramienta de desarrollador [Caché global de ensamblados (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md), que se suministra con Windows SDK.  
  
    > [!NOTE]
    > En escenarios de implementación, use Windows Installer para instalar los ensamblados en la caché global de ensamblados. Utilice la herramienta Caché global de ensamblados solo en escenarios de desarrollo, porque no proporciona funciones de recuento de referencias de ensamblados y otras características que se incluyen con Windows Installer.  
  
 A partir de .NET Framework 4, la ubicación predeterminada de la caché global de ensamblados es **%windir%\Microsoft.NET\assembly**. En versiones anteriores de .NET Framework, la ubicación predeterminada es **%windir%\assembly**.  
  
 Con frecuencia, los administradores protegen el directorio systemroot con una lista de control de acceso (ACL) para controlar el acceso de escritura y ejecución. Puesto que la caché global de ensamblados está instalada en un subdirectorio del directorio systemroot, hereda la ACL de dicho directorio. Se recomienda que solo los usuarios que tengan privilegios de administrador puedan eliminar archivos de la caché global de ensamblados.  
  
 Los ensamblados implementados en la caché global de ensamblados deben tener nombres seguros. Cuando se agrega un ensamblado a la caché global de ensamblados, se realizan comprobaciones de integridad de todos los archivos que componen el ensamblado. La caché realiza estas comprobaciones de integridad para garantizar que no se ha manipulado ningún ensamblado, por ejemplo, cuando se ha modificado un archivo pero el manifiesto no refleja el cambio.  
  
## <a name="see-also"></a>Vea también

- [Ensamblados de .NET](../../standard/assembly/index.md)
- [Trabajar con ensamblados y la memoria caché global de ensamblados](working-with-assemblies-and-the-gac.md)
- [Ensamblados con nombre seguro](../../standard/assembly/strong-named.md)
