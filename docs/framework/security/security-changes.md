---
title: Cambios de seguridad en .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- Allow Partially Trusted Callers attribute
- .NET Framework 4, security changes
- .NET Framework security
- security-transparent code
- security-critical code
- code access security, changes
ms.assetid: 5e87881c-9c13-4b52-8ad1-e34bb46e8aaa
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c62a469b3e31283e5790c747092a8fe504ef8c2a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670161"
---
# <a name="security-changes-in-the-net-framework"></a>Cambios de seguridad en .NET Framework
El cambio más importante en la seguridad de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] es la adopción de nombres seguros. Consulte [Enhanced Strong Naming](../../../docs/framework/app-domains/enhanced-strong-naming.md) para obtener una descripción de estos cambios.  
  
 .NET Framework proporciona un modelo de seguridad de dos niveles para las aplicaciones administradas. Las aplicaciones de la[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] se ejecutan en un contenedor de seguridad de Windows que restringe el acceso a los recursos. Dentro de ese contenedor, la ejecución de las aplicaciones administradas es de plena confianza. Desde la perspectiva de la seguridad de acceso del código (CAS), no hay nada que un desarrollador pueda hacer para elevar los privilegios. Para obtener información sobre los privilegios concedidos por Windows, consulte [Declaraciones de funcionalidades de las aplicaciones (aplicaciones de la Tienda Windows)](https://go.microsoft.com/fwlink/?LinkId=230436) en el Centro de desarrollo de Windows. Para obtener información sobre cómo crear una aplicación de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] , consulte [Crear la primera aplicación de la Tienda Windows con C# o Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461).
