---
title: Interoperabilidad COM sin registro
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], interop
- COM interop, registration-free COM interop
- registration-free COM interop
- manifests [.NET Framework]
- registration-free activation
- object activation
- registration-free COM interop, about registration-free COM interop
ms.assetid: 90f308b9-82dc-414a-bce1-77e0155e56bd
ms.openlocfilehash: f73bb2ac9e1b942c08f83507589b534d7e67748d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124969"
---
# <a name="registration-free-com-interop"></a>Interoperabilidad COM sin registro
La interoperabilidad COM sin registrar activa un componente sin usar el Registro de Windows para almacenar la información de los ensamblados. En vez de registrar un componente en un equipo durante la implementación, se crean archivos de manifiesto del estilo de Win32 en tiempo de diseño, con información sobre enlace y activación. En lugar de las claves del Registro, estos archivos de manifiesto dirigen la activación de un objeto.  
  
 Activar los ensamblados sin registrarlos en lugar de registrarlos durante la implementación ofrece dos ventajas:  
  
- Puede controlar qué versión del archivo DLL se activa cuando hay más de una versión instalada en un equipo.  
  
- Los usuarios finales pueden usar XCOPY o FTP para copiar la aplicación en un directorio adecuado de su equipo. La aplicación puede entonces ejecutarse desde ese directorio.  
  
 En esta sección se describen los dos tipos de manifiestos que se necesitan para la interoperabilidad COM sin registro: manifiestos de aplicación y de componente. Estos manifiestos son archivos XML. Un manifiesto de aplicación, creado por un desarrollador de aplicaciones, contiene metadatos que describen los ensamblados y las dependencias de ensamblado. Un manifiesto de componente, creado por un desarrollador de componentes, contiene información que se encontraría en el Registro de Windows.  
  
### <a name="requirements-for-registration-free-com-interop"></a>Requisitos para interoperabilidad COM sin registro  
  
1. La compatibilidad para la interoperabilidad COM sin registro varía ligeramente según el tipo de ensamblado de biblioteca; en concreto, si el ensamblado es no administrado (COM en paralelo) o administrado (basado en .NET). En la tabla siguiente se muestra los requisitos de sistema operativo y de versión de .NET Framework para cada tipo de ensamblado.  
  
    |Tipo de ensamblado|Sistema operativo|Versión de .NET Framework|  
    |-------------------|----------------------|----------------------------|  
    |COM en paralelo|Microsoft Windows XP|No es necesario.|  
    |Basado en .NET|Windows XP con SP2|NET Framework versión 1.1 o posterior.|  
  
     La familia Windows Server 2003 también admite interoperabilidad COM sin registro para ensamblados basados en .NET.  
  
     Para que una clase basada en .NET sea compatible con la activación sin registro desde COM, la clase deben tener un constructor sin parámetros y debe ser pública.  
  
### <a name="configuring-com-components-for-registration-free-activation"></a>Configurar componentes COM para la activación sin registro  
  
1. Para que un componente COM participe en la activación sin registro, debe implementarse como un ensamblado en paralelo. Los ensamblados en paralelo son ensamblados no administrados.  Para más información, consulte el tema sobre [cómo usar ensamblados en paralelo](/windows/desktop/SbsCs/using-side-by-side-assemblies).  
  
     Para usar ensamblados COM en paralelo, un desarrollador de aplicaciones basadas en .NET debe proporcionar un manifiesto de aplicación con información sobre enlace y activación. La compatibilidad con los ensamblados en paralelo no administrados está integrada en el sistema operativo Windows XP. El tiempo de ejecución COM, admitido por el sistema operativo, busca un manifiesto de aplicación para obtener información de activación cuando el componente que se va a activar no está en el Registro.  
  
     La activación sin registro es opcional para los componentes COM instalados en Windows XP. Para obtener instrucciones detalladas acerca de cómo agregar un ensamblado en paralelo a una aplicación, consulte el tema sobre [cómo usar ensamblados en paralelo](/windows/desktop/SbsCs/using-side-by-side-assemblies).  
  
    > [!NOTE]
    > La ejecución en paralelo es una característica de .NET Framework que permite ejecutar varias versiones del tiempo de ejecución y varias versiones de las aplicaciones y los componentes que usan una versión del tiempo de ejecución, en el mismo equipo y al mismo tiempo. La ejecución en paralelo y los ensamblados en paralelo son mecanismos diferentes para proporcionar una funcionalidad en paralelo.  
  
## <a name="see-also"></a>Vea también

- [Cómo: Configurar componentes COM basados en .NET Framework para la activación sin registro](configure-net-framework-based-com-components-for-reg.md)
