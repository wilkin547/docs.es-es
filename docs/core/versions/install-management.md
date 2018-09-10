---
title: Administrar las instalaciones de .NET Core
description: Administre varias versiones del SDK y Runtime de .NET Core en el equipo, y trabaje con las estrategias de instalación en paralelo.
author: leecow
ms.author: wiwagn
ms.date: 08/22/2018
ms.openlocfilehash: 06c3f43e7917efb8fd31898044d8f5d920c2cada
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43523683"
---
# <a name="manage-net-core-installations"></a>Administrar las instalaciones de .NET Core

.NET Core permite la coexistencia de varias versiones del SDK y Runtime en paralelo, lo que ofrece flexibilidad a la dependencia de versiones tanto para compilar como para ejecutar aplicaciones de .NET Core. Este tipo de instalación y estos comportamientos de actualización automática de versiones tienen importantes ventajas, pero una destacada desventaja. A medida que se instalan las actualizaciones del SDK de .NET Core o .NET Core Runtime, las versiones anteriores permanecen en el disco. Con el tiempo, esta instalación de numerosas versiones incrementa el uso de disco. Se han publicado más de 50 actualizaciones del SDK de .NET Core. Es posible que haya muchas versiones del SDK y Runtime instaladas en el sistema que se podrían quitar.

## <a name="safe-to-remove"></a>¿Es seguro quitarlas?

Los comportamientos de la [selección de la versión de .NET Core](selection.md) y la compatibilidad de runtime de .NET Core en diferentes actualizaciones permite quitar de forma segura las versiones anteriores. Las actualizaciones de .NET Core Runtime son compatibles con una "banda" de versión principal, como 1.x y 2.x. Además, normalmente las versiones más recientes del SDK de .NET Core mantienen la capacidad de crear aplicaciones destinadas a versiones anteriores del tiempo de ejecución de una forma compatible.

En general, solo se necesita el SDK más reciente y la última versión de revisión de los runtimes necesarios para la aplicación. Los casos en los que se conservan versiones anteriores del SDK o Runtime incluyen el mantenimiento de aplicaciones basadas en project.json.  A menos que la aplicación tenga motivos concretos para utilizar SDK o runtimes anteriores, puede quitar las versiones anteriores.

Los métodos para quitar .NET Core varían en función de la plataforma y han cambiado un poco entre versiones de .NET Core. Para obtener más información sobre cómo quitar versiones de .NET Core que ya no se necesitan, vea [How to remove the .NET Core Runtime and SDK](remove-runtime-sdk-versions.md) (Cómo quitar el SDK y Runtime de .NET Core) en la [documentación de .NET Core](../index.md).
