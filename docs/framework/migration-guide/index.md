---
title: 'Guía de migración a .NET Framework 4.8, 4.7, 4.6 y 4.5 '
ms.custom: updateeachrelease
ms.date: 04/18/2019
helpviewer_keywords:
- .NET Framework, migrating applications to
- migration, .NET Framework
ms.assetid: 02d55147-9b3a-4557-a45f-fa936fadae3b
ms.openlocfilehash: 2fa992e1c0897d360f322581888c51dca8d8a734
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73974986"
---
# <a name="migration-guide-to-the-net-framework-48-47-46-and-45"></a>Guía de migración a .NET Framework 4.8, 4.7, 4.6 y 4.5

Si creó la aplicación con una versión anterior de .NET Framework, normalmente puede actualizarla con facilidad a .NET Framework 4.5 y sus versiones secundarias (4.5.1 y 4.5.2), .NET Framework 4.6 y sus versiones secundarias (4.6.1 y 4.6.2), .NET Framework 4.7 y sus versiones secundarias (4.7.1 y 4.7.2) o .NET Framework 4.8. Abra el proyecto en Visual Studio. Si el proyecto se creó en una versión anterior de Visual Studio, se abre automáticamente el cuadro de diálogo **Compatibilidad de proyectos**. Para más información sobre cómo actualizar un proyecto en Visual Studio, consulte [Portar, migrar y actualizar proyectos de Visual Studio](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects) y [Compatibilidad y destinatarios de la plataforma de Visual Studio 2019](/visualstudio/releases/2019/compatibility).

 Sin embargo, como se han realizado ciertos cambios en .NET Framework, deberá modificar el código. Es posible que también quiera aprovechar las funcionalidades nuevas de .NET Framework 4.5, .NET Framework 4.6 o .NET Framework 4.7 y sus versiones secundarias correspondientes, o de .NET Framework 4.8. El proceso de realizar estos tipos de cambios en la aplicación para adaptarla a una nueva versión de .NET Framework se conoce normalmente como *migración*. Si no es necesario migrar la aplicación, puede ejecutarla en .NET Framework 4.5 o en una versión posterior sin tener que recompilarla.

## <a name="migration-resources"></a>Recursos de migración

Consulte los documentos siguientes antes de migrar la aplicación de versiones anteriores de .NET Framework a la versión 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2 o 4.8:

- Consulte [Versiones y dependencias](versions-and-dependencies.md) para conocer la versión de CLR subyacente a cada versión de .NET Framework y obtener instrucciones sobre cómo establecer correctamente el destino de sus aplicaciones.

- Consulte [Compatibilidad de aplicaciones](application-compatibility.md) para información sobre el entorno de ejecución y los cambios de destino que puedan afectar a la aplicación y cómo abordarlos.

- Consulte [Lo obsoleto en la biblioteca de clases](../whats-new/whats-obsolete.md) para determinar los tipos o miembros del código que quedaron obsoletos y las alternativas recomendadas.

- Consulte [Novedades](../whats-new/index.md) para obtener descripciones sobre las nuevas características que tal vez desee agregar a la aplicación.

## <a name="see-also"></a>Vea también

- [Compatibilidad de aplicaciones](application-compatibility.md)
- [Migración desde .NET Framework 1.1](migrating-from-the-net-framework-1-1.md)
- [Compatibilidad de versiones](version-compatibility.md)
- [Versiones y dependencias](versions-and-dependencies.md)
- [Cómo: Configurar una aplicación para que admita .NET Framework 4 o versiones posteriores](how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- [Novedades](../whats-new/index.md)
- [Lo obsoleto en la biblioteca de clases](../whats-new/whats-obsolete.md)
- [Directiva de soporte técnico oficial de .NET Framework](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework)
- [Problemas de migración de .NET Framework 4](net-framework-4-migration-issues.md)
