---
title: Conceptos básicos sobre la seguridad de acceso del código
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], code access security
ms.assetid: 4eaa6535-d9fe-41a1-91d8-b437cfc16921
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8d5a5658fcb6bbba72938a16a9e5c82fd779e2e3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352963"
---
# <a name="code-access-security-basics"></a>Conceptos básicos sobre la seguridad de acceso del código

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

Todas las aplicaciones que tengan como destino Common Language Runtime (es decir, todas las aplicaciones administradas) deben interactuar con el sistema de seguridad del runtime. Cuando se carga una aplicación administrada, su host le concede automáticamente un conjunto de permisos. Estos permisos están determinados por la configuración de seguridad local del host o por el espacio aislado en el que se encuentra la aplicación. En función de estos permisos, la aplicación se ejecutará correctamente o generará una excepción de seguridad.

El host predeterminado para las aplicaciones de escritorio permite que el código se ejecute con plena confianza. Por lo tanto, si la aplicación tiene como destino el escritorio, tendrá un conjunto de permisos no restringido. Otros hosts o espacios aislados proporcionan un conjunto de permisos limitado para las aplicaciones. Dado que el conjunto de permisos puede cambiar de un host a otro, deberá diseñar la aplicación para que tan solo use los permisos que permite el host de destino.

Debe estar familiarizado con los siguientes conceptos de seguridad de acceso del código para escribir aplicaciones eficaces que tengan como destino Common Language Runtime:

- **Código de seguridad de tipos**: Código de seguridad de tipos es código que sólo obtiene acceso a tipos siguiendo métodos permitidos y bien definidos. Por ejemplo, dada una referencia de objeto válido, el código con seguridad de tipos puede tener acceso a la memoria en desplazamientos fijos que se corresponden con miembros de campo reales. El código no tiene seguridad de tipos si tiene acceso a la memoria en desplazamientos arbitrarios fuera del intervalo de memoria que pertenece a esos campos del objeto expuestos públicamente. Para que el código pueda beneficiarse de la seguridad de acceso del código, use un compilador que genere código con seguridad de tipos comprobable. Para obtener más información, consulte el [escribir tipo código comprobable](#typesafe_code) sección más adelante en este tema.

- **Sintaxis imperativa y declarativa**: El código que tiene como destino common language runtime puede interactuar con el sistema de seguridad al solicitar permisos, exigir que los llamadores tengan los permisos especificados e invalidar ciertas opciones de seguridad (otorgados suficientes privilegios). Para interactuar mediante programación con el sistema de seguridad de .NET Framework se usan dos formas de sintaxis: sintaxis declarativa y la sintaxis imperativa. Las llamadas declarativas se realizan mediante atributos y las llamadas imperativas se realizan con nuevas instancias de clases dentro del código. Hay llamadas que solo se pueden realizar de manera imperativa, otras solo de forma declarativa y algunas se pueden realizar de ambas maneras.

- **Bibliotecas de clases seguras**: Una biblioteca de clases seguras usa peticiones de seguridad para asegurarse de que los llamadores de la biblioteca tienen permiso para acceder a los recursos que expone la biblioteca. Por ejemplo, una biblioteca de clases segura podría tener un método para crear archivos que requiera que los llamadores tengan permisos para crear archivos. .NET Framework consta de bibliotecas de clases seguras. Debe tener en cuenta los permisos necesarios para el acceso a cualquier biblioteca que use el código. Para obtener más información, consulte el [usando bibliotecas de clases seguras](#secure_library) sección más adelante en este tema.

- **El código transparente**: A partir de la [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], además de identificar los permisos específicos, también debe determinar si el código debe ejecutarse como transparente en seguridad. El código transparente en seguridad no puede llamar a tipos o miembros que se identifican como críticos para la seguridad. Esta regla se aplica a las aplicaciones de plena confianza y a las de confianza parcial. Para obtener más información, consulte [código transparente en seguridad](../../../docs/framework/misc/security-transparent-code.md).

<a name="typesafe_code"></a>

## <a name="writing-verifiably-type-safe-code"></a>Escritura de código con seguridad de tipos comprobable

La compilación Just-In-Time (JIT) ejecuta un proceso de comprobación que examina el código e intenta determinar si el código tiene seguridad de tipos. Se llama al código que se ha demostrado durante la comprobación de seguridad de tipos *código seguro comprobable*. Es posible que el código tenga seguridad de tipos aunque no se pueda comprobar que sea así debido a las limitaciones del proceso de comprobación o del compilador. No todos los lenguajes tienen seguridad de tipos y algunos compiladores de lenguaje, como Microsoft Visual C++, no pueden generar código administrado con seguridad de tipos comprobable. Para determinar si su compilador de lenguaje genera código con seguridad de tipos comprobable, consulte la documentación del compilador. Si usa un compilador de lenguaje que genera código seguro comprobable solo cuando se evitan determinadas construcciones de lenguaje, desea utilizar el [herramienta PEVerify](../../../docs/framework/tools/peverify-exe-peverify-tool.md) para determinar si el código tiene seguridad de tipos comprobable.

El código sin seguridad de tipos comprobable puede intentar ejecutarse si la directiva de seguridad permite al código omitir esta comprobación. Sin embargo, dado que la seguridad de tipos es una parte esencial del mecanismo de runtime para aislar los ensamblados, la seguridad no se puede aplicar de forma confiable si el código infringe las reglas de seguridad de tipos. De forma predeterminada, el código sin seguridad de tipos solo se puede ejecutar si se origina desde el equipo local. Por lo tanto, el código móvil debe tener seguridad de tipos.

<a name="secure_library"></a>

## <a name="using-secure-class-libraries"></a>Uso de bibliotecas de clases seguras

Si el código solicita y se le conceden los permisos requeridos por la biblioteca de clases, se le permitirá tener acceso a la biblioteca y los recursos que expone la biblioteca estarán protegidos frente a accesos no autorizados. Si el código no tiene los permisos adecuados, no podrá tener acceso a la biblioteca de clases y el código malintencionado no podrá usar el código para obtener acceso indirectamente a los recursos protegidos. El resto de código que llame a su código también deber tener permiso de acceso a la biblioteca. Si no es así, su código tampoco podrá ejecutarse.

Seguridad de acceso del código no elimina la posibilidad de que se produzcan errores humanos al escribir código. Sin embargo, si la aplicación usa bibliotecas de clases seguras para obtener acceso a recursos protegidos, se reduce el riesgo de seguridad para el código de la aplicación, ya que las bibliotecas de clases se examinan detenidamente para detectar posibles problemas de seguridad.

## <a name="declarative-security"></a>Seguridad declarativa

Sintaxis de seguridad declarativa usa [atributos](../../../docs/standard/attributes/index.md) para colocar la información de seguridad en el [metadatos](../../../docs/standard/metadata-and-self-describing-components.md) del código. Los atributos se pueden colocar en el nivel de ensamblado, clase o miembro para indicar el tipo de solicitud, petición o invalidación que desea usar. Las solicitudes se usan en aplicaciones destinadas a Common Language Runtime para informar al sistema de seguridad de runtime sobre los permisos que la aplicación necesita o no desea. Las peticiones e invalidaciones se usan en las bibliotecas para ayudar a proteger los recursos de los llamadores o para invalidar el comportamiento de seguridad predeterminado.

> [!NOTE]
> En [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]se introdujeron cambios importantes tanto en el modelo de seguridad de .NET Framework como en la terminología. Para obtener más información sobre estos cambios, consulte [cambios de seguridad](../../../docs/framework/security/security-changes.md).

Para usar llamadas de seguridad declarativas, debe inicializar los datos de estado del objeto de permiso para que represente la forma concreta del permiso necesario. Cada permiso integrado tiene un atributo al que se pasa una enumeración <xref:System.Security.Permissions.SecurityAction> para describir el tipo de operación de seguridad que se desea realizar. Sin embargo, los permisos también aceptan parámetros propios exclusivos.

El siguiente fragmento de código muestra la sintaxis declarativa para solicitar que los llamadores del código tengan un permiso personalizado denominado `MyPermission`. Este permiso es un permiso personalizado hipotético y no existe en .NET Framework. En este ejemplo, la llamada declarativa se coloca directamente antes de la definición de clase, lo que especifica que este permiso se aplica en el nivel de clase. Se pasa al atributo un **SecurityAction.Demand** estructura para especificar que los llamadores deben tener este permiso para ejecutar.

```vb
<MyPermission(SecurityAction.Demand, Unrestricted = True)> Public Class MyClass1

   Public Sub New()
      'The constructor is protected by the security call.
   End Sub

   Public Sub MyMethod()
      'This method is protected by the security call.
   End Sub

   Public Sub YourMethod()
      'This method is protected by the security call.
   End Sub
End Class
```

```csharp
[MyPermission(SecurityAction.Demand, Unrestricted = true)]
public class MyClass
{
   public MyClass()
   {
      //The constructor is protected by the security call.
   }

   public void MyMethod()
   {
      //This method is protected by the security call.
   }

   public void YourMethod()
   {
      //This method is protected by the security call.
   }
}
```

## <a name="imperative-security"></a>Seguridad imperativa

La sintaxis de seguridad imperativa emite una llamada de seguridad mediante la creación de una nueva instancia del objeto de permiso que se desea invocar. La sintaxis imperativa se puede usar para realizar peticiones e invalidaciones, pero no solicitudes.

Antes de realizar la llamada de seguridad, debe inicializar los datos de estado del objeto de permiso para que represente la forma concreta del permiso necesario. Por ejemplo, al crear un <xref:System.Security.Permissions.FileIOPermission> objeto, puede utilizar el constructor para inicializar el **FileIOPermission** para que represente el acceso ilimitado a todos los archivos o ningún acceso a los archivos de objeto. O bien, puede usar otra **FileIOPermission** objeto, pasando el objeto de parámetros que indican el tipo de acceso que desea para representar (es decir, lectura, anexar o escritura) y qué archivos desea que el objeto proteja.

Además de usar la sintaxis de seguridad imperativa para invocar un solo objeto de seguridad, puede usarlo para inicializar un grupo de permisos de un conjunto de permisos. Por ejemplo, esta técnica es la única manera confiable de realizar [assert](../../../docs/framework/misc/using-the-assert-method.md) llama en varios permisos en un método. Use las clases <xref:System.Security.PermissionSet> y <xref:System.Security.NamedPermissionSet> para crear un grupo de permisos y, a continuación, llame al método apropiado para invocar la llamada de seguridad deseada.

La sintaxis imperativa se puede usar para realizar peticiones e invalidaciones, pero no solicitudes. Cuando la información que necesita para inicializar el estado de permiso solo se revela en tiempo de ejecución, puede usar la sintaxis imperativa para las peticiones e invalidaciones en lugar de la sintaxis declarativa. Por ejemplo, si desea asegurarse de que los llamadores tienen permiso para leer un archivo determinado, pero no conoce el nombre de ese archivo hasta el tiempo de ejecución, use una petición imperativa. También puede usar comprobaciones imperativas en lugar de comprobaciones declarativas cuando necesita determinar en tiempo de ejecución si una condición se mantiene y, en función del resultado de la prueba, realizar una petición de seguridad (o no).

El siguiente fragmento de código muestra la sintaxis imperativa para solicitar que los llamadores del código tengan un permiso personalizado denominado `MyPermission`. Este permiso es un permiso personalizado hipotético y no existe en .NET Framework. Una nueva instancia de `MyPermission` se crea en `MyMethod`, protegiendo solo este método con la llamada de seguridad.

```vb
Public Class MyClass1

   Public Sub New()

   End Sub

   Public Sub MyMethod()
      'MyPermission is demanded using imperative syntax.
      Dim Perm As New MyPermission()
      Perm.Demand()
      'This method is protected by the security call.
   End Sub

   Public Sub YourMethod()
      'YourMethod 'This method is not protected by the security call.
   End Sub
End Class
```

```csharp
public class MyClass {
   public MyClass(){

   }

   public void MyMethod() {
       //MyPermission is demanded using imperative syntax.
       MyPermission Perm = new MyPermission();
       Perm.Demand();
       //This method is protected by the security call.
   }

   public void YourMethod() {
       //This method is not protected by the security call.
   }
}
```

## <a name="using-managed-wrapper-classes"></a>Utilizar clases contenedoras administradas

La mayoría de las aplicaciones y los componentes (excepto las bibliotecas seguras) no deben llamar directamente a código no administrado. Hay varias razones para ello. Si el código llama directamente a código no administrado, no podrá ejecutarse en muchas circunstancias porque el código debe disponer de un alto nivel de confianza para llamar a código nativo. Si se modifica la directiva para permitir que esa aplicación se ejecute, ello podrá debilitar significativamente la seguridad del sistema, dando libertad a la aplicación para que realice prácticamente cualquier operación.

Además, el código que tiene permiso de acceso a código no administrado probablemente puede realizar casi cualquier operación mediante una llamada a una API no administrada. Por ejemplo, no es necesario el código que tiene permiso para llamar a código no administrado <xref:System.Security.Permissions.FileIOPermission> para tener acceso a un archivo; simplemente puede llamar a un archivo (Win32) no administrado API directamente, omitiendo el archivo administrada API que requiera **FileIOPermission**. Si el código administrado tiene permiso para llamar a código no administrado y llama directamente al código no administrado, el sistema de seguridad no podrá imponer restricciones de seguridad de manera confiable, ya que el runtime no puede aplicar dichas restricciones al código no administrado.

Si desea que la aplicación realice una operación que requiere el acceso a código no administrado, deberá hacerlo a través de una clase administrada de confianza que encapsule la funcionalidad necesaria (si esta clase existe). No cree una clase contenedora usted mismo si ya existe una en la biblioteca de clases seguras. La clase contenedora, que debe tener un alto grado de confianza que le permita realizar la llamada a código no administrado, es responsable de exigir que sus llamadores tengan los permisos adecuados. Si usa la clase contenedora, el código solo necesita solicitar y recibir los permisos que requiere la clase contenedora.

## <a name="see-also"></a>Vea también

- <xref:System.Security.PermissionSet>
- <xref:System.Security.Permissions.FileIOPermission>
- <xref:System.Security.NamedPermissionSet>
- <xref:System.Security.Permissions.SecurityAction>
- [Assert](../../../docs/framework/misc/using-the-assert-method.md)
- [Seguridad de acceso del código](../../../docs/framework/misc/code-access-security.md)
- [Code Access Security Basics](../../../docs/framework/misc/code-access-security-basics.md) (Conceptos básicos sobre la seguridad de acceso del código)
- [Atributos](../../../docs/standard/attributes/index.md)
- [Metadatos y componentes autodescriptivos](../../../docs/standard/metadata-and-self-describing-components.md)
