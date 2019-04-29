---
title: Seguridad e introducción de datos por el usuario
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- security [.NET Framework], user input
- user input, security
- secure coding, user input
- code security, user input
ms.assetid: 9141076a-96c9-4b01-93de-366bb1d858bc
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 27818d5e1779cd6e10e11830f91a20a3e638639a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61933788"
---
# <a name="security-and-user-input"></a>Seguridad e introducción de datos por el usuario
Los datos de usuario, que consisten en cualquier tipo de entrada (datos de una solicitud web o dirección URL, entrada a los controles de una aplicación de Microsoft Windows Forms etc.), pueden afectar negativamente al código, porque a menudo se utilizan esos datos directamente como parámetros para llamar a otro código. Esta situación es análoga al código malintencionado que llama a su código con parámetros extraños, y se deben tomar las mismas precauciones. La entrada del usuario es en realidad más difícil de proteger, porque no hay ningún marco de pila para realizar el seguimiento de la presencia de datos que no sean de confianza.  
  
 Estos son los errores de seguridad más sutiles y más difíciles de localizar porque, aunque pueden existir en el código aparentemente no relacionado con la seguridad, son una puerta de enlace para que pasen datos maliciosos a otro código. Para buscar estos errores, siga cualquier tipo de datos de entrada, imagine cuál puede ser el intervalo de valores posibles y considere si el código que ve estos datos puede controlar todos esos casos. Puede corregir estos errores mediante la comprobación del intervalo y el rechazo de cualquier entrada que no puede controlar el código.  
  
 A continuación se indican algunas consideraciones importantes que afectan a los datos de usuario:  
  
- Los datos de usuario de una respuesta del servidor se ejecutan en el contexto del sitio del servidor en el cliente. Si el servidor web toma los datos de usuario y los inserta en la página web, podría incluir, por ejemplo, una etiqueta **\<script>** y ejecutarlos como si se encontrase en el servidor.  
  
- Recuerde que el cliente puede solicitar cualquier dirección URL.  
  
- Tenga en cuenta las rutas de acceso complicadas o no válidas:  
  
    - ..\, rutas de acceso extremadamente largas.  
  
    - Uso de caracteres comodín (*).  
  
    - Expansión de token (%token%).  
  
    - Formatos extraños de rutas de acceso con un significado especial.  
  
    - Nombres de flujos de sistema de archivo alternativos, como `filename::$DATA`.  
  
    - Versiones cortas de los nombres de archivo como `longfi~1` para `longfilename`.  
  
- Recuerde que Eval(userdata) puede hacer cualquier cosa.  
  
- Tenga cuidado de los enlaces tardíos en un nombre que incluye algunos datos de usuario.  
  
- Si está trabajando con datos de web, tenga en cuenta las distintas secuencias de escape permitidas, como:  
  
    - Secuencias de escape hexadecimales (%nn).  
  
    - Secuencias de escape Unicode (%nnn).  
  
    - Secuencias de escape UTF-8 excesivamente largas (%nn%nn).  
  
    - Secuencias de escape dobles (%nn se convierte en %mmnn, donde %mm es el escape para '%').  
  
- Tenga cuidado con los nombres de usuario que pueden tener más de un formato canónico. Por ejemplo, a menudo puede utilizar cualquier forma de MIDOMINIO\\*nombreUsuario* o de *nombreUsuario*@mydomain.example.com.  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de codificación segura](../../../docs/standard/security/secure-coding-guidelines.md)
