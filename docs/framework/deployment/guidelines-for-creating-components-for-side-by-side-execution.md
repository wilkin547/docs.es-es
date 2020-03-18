---
title: Instrucciones para crear componentes para la ejecución en paralelo
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, multiple application versions
- side-by-side execution, multiple component versions
ms.assetid: 5c540161-6e40-42e9-be92-6175aee2c46a
ms.openlocfilehash: 42d0e2d85517d4a8fb443db9b63e6b893267caca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73121586"
---
# <a name="guidelines-for-creating-components-for-side-by-side-execution"></a>Instrucciones para crear componentes para la ejecución en paralelo
Siga estas instrucciones generales para crear aplicaciones administradas o componentes diseñados para la ejecución en paralelo:  
  
- Enlazar la identidad de tipo a una versión determinada de un archivo.  
  
     Common Language Runtime enlaza la identidad de tipo a una versión de archivo en particular mediante el uso de ensamblados de nombre seguro. Para poder crear una aplicación o un componente para la ejecución en paralelo, es necesario asignar un nombre seguro a todos los ensamblados. Esto crea la identidad de tipo precisa y garantiza que cualquier resolución de tipos se dirige al archivo correcto. Un ensamblado con nombre seguro contiene la información de versión, referencia cultural y editor que el runtime usa para localizar el archivo correcto y satisfacer una solicitud de enlace.  
  
- Usar almacenamiento con identificación de versión.  
  
     El runtime usa la caché de ensamblados global para proporcionar un almacenamiento con identificación de versión. La caché global de ensamblados es una estructura de directorios con identificación de versión instalada en todos los equipos que usan .NET Framework. Los ensamblados instalados en la caché global de ensamblados no se sobrescriben cuando se instala una nueva versión de dicho ensamblado.  
  
- Crear una aplicación o componente que se ejecute de forma aislada.  
  
     Una aplicación o componente que se ejecuta de forma aislada debe administrar los recursos para evitar conflictos cuando dos instancias de la aplicación o componente se ejecutan simultáneamente. La aplicación o componente debe usar también una estructura de archivos específica de la versión.  
  
## <a name="application-and-component-isolation"></a>Aislamiento de aplicación y componente  
 El aislamiento es una de las claves en el diseño de una aplicación o componente para la ejecución en paralelo. La aplicación o componente debe administrar todos los recursos —especialmente la E/S de archivos— de forma aislada. Siga estas instrucciones para asegurarse de que su aplicación o componente se ejecuta de forma aislada:  
  
- Escriba en el registro de una manera específica de la versión. Almacene los valores en subárboles o claves que indiquen la versión y no comparta información ni el estado entre las versiones de un componente. Esto evita que dos aplicaciones o componentes que se ejecutan al mismo tiempo sobrescriban la información.  
  
- Asegúrese de que los objetos de kernel con nombre sean específicos de la versión para que no se produzca una condición de carrera. Por ejemplo, una condición de carrera se produce cuando dos semáforos de dos versiones de la misma aplicación se esperan entre sí.  
  
- Use nombres de archivos y directorios con identificación de versión. Esto significa que las estructuras de archivos deben basarse en la información de versión.  
  
- Cree grupos y cuentas de usuario de forma específica a una versión. Los grupos y cuentas de usuarios creados por una aplicación deben identificarse por versión. No comparta cuentas de usuarios y grupos entre distintas versiones de una aplicación.  
  
## <a name="installing-and-uninstalling-versions"></a>Instalar y desinstalar versiones  
 Al diseñar una aplicación para la ejecución en paralelo, siga estas instrucciones relativas a la instalación y desinstalación de versiones:  
  
- No elimine información del Registro que pueda ser necesaria para otras aplicaciones que se ejecutan en una versión diferente de .NET Framework.  
  
- No reemplace información del Registro que pueda ser necesaria para otras aplicaciones que se ejecutan con una versión diferente de .NET Framework.  
  
- No anule el registro de componentes COM que puedan ser necesarios para otras aplicaciones que se ejecutan en una versión diferente de .NET Framework.  
  
- No cambie **InprocServer32** ni otras entradas del Registro de un servidor COM que ya se haya registrado.  
  
- No elimine cuentas de usuario ni grupos que puedan ser necesarios para otras aplicaciones que se ejecutan en una versión diferente de .NET Framework.  
  
- No agregue nada al Registro que contenga una ruta de acceso sin versión.  
  
## <a name="file-version-number-and-assembly-version-number"></a>Número de versión de archivo y número de versión de ensamblado  
 La versión del archivo es un recurso de versión de Win32 que no es usada por el runtime. En general, la versión del archivo debe actualizarse incluso para una actualización en contexto. Dos archivos idénticos pueden tener información de versión de archivo diferente y dos archivos distintos pueden tener la misma información de versión de archivo.  
  
 El runtime usa la versión del ensamblado para el enlace de ensamblados. El runtime considera ensamblados diferentes a dos ensamblados idénticos con un número de versión distinto.  
  
 La [herramienta de caché global de ensamblados (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) permite reemplazar un ensamblado solo cuando el número de versión del archivo es más reciente. Generalmente, el programa de instalación no instala encima de un ensamblado a menos que el número de versión del ensamblado sea mayor.  
  
## <a name="see-also"></a>Vea también

- [Ejecución en paralelo](side-by-side-execution.md)
- [Cómo: Habilitar y deshabilitar redireccionamiento de enlaces automático](../configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)
