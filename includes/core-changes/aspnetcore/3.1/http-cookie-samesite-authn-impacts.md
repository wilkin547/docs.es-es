---
ms.openlocfilehash: 8b6d334677991382d235fd53cd3c98e3a77d650d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539623"
---
### <a name="http-browser-samesite-changes-impact-authentication"></a>HTTP: Los cambios de SameSite en los exploradores afectan a la autenticación.

Algunos exploradores, como Chrome y Firefox, han realizado cambios importantes en sus implementaciones de `SameSite` para las cookies. Los cambios afectan a escenarios de autenticación remota, como OpenID Connect y WS-Federation, que deben no participar mediante el envío de `SameSite=None`. Sin embargo, `SameSite=None` se interrumpe en iOS 12 y en algunas versiones anteriores de otros exploradores. La aplicación debe detectar estas versiones y omitir `SameSite`.

Para obtener información sobre esta incidencia, vea [dotnet/aspnetcore#14996](https://github.com/dotnet/aspnetcore/issues/14996).

#### <a name="version-introduced"></a>Versión introducida

3.1, versión preliminar 1

#### <a name="old-behavior"></a>Comportamiento anterior

`SameSite` es una extensión de proyecto de norma de 2016 para cookies HTTP. Su objetivo era mitigar la falsificación de solicitud entre sitios (CSRF). Originalmente se diseñó como una característica en la que los servidores participaban si agregaban los nuevos parámetros. ASP.NET Core 2.0 agregó compatibilidad inicial con `SameSite`.

#### <a name="new-behavior"></a>Comportamiento nuevo

Google ha propuesto un nuevo proyecto de norma que no es compatible con versiones anteriores. La norma cambia el modo predeterminado a `Lax` y agrega una nueva entrada `None` para no participar. `Lax` basta para la mayoría de las cookies de aplicación, aunque interrumpe escenarios entre sitios como el inicio de sesión de OpenID Connect y WS-Federation. La mayoría de los inicios de sesión de OAuth no se ven afectados debido a las diferencias respecto al flujo de la solicitud. El nuevo parámetro `None` origina problemas de compatibilidad con los clientes que han implementado el proyecto de norma anterior (por ejemplo, iOS 12). Chrome 80 va a incluir los cambios. Vea [Actualizaciones de SameSite](https://www.chromium.org/updates/same-site) para conocer la escala de tiempo de lanzamiento del producto Chrome.

ASP.NET Core 3.1 se ha actualizado para implementar el nuevo comportamiento de `SameSite`. La actualización vuelve a definir el comportamiento de `SameSiteMode.None` para emitir `SameSite=None` y agrega un nuevo valor `SameSiteMode.Unspecified` para omitir el atributo `SameSite`. Todas las API de cookies ahora tienen como valor predeterminado `Unspecified`, aunque algunos componentes que usan cookies establecen valores más específicos en sus escenarios, como la correlación de OpenID Connect y las cookies nonce.

Para obtener información sobre otros cambios recientes en esta área, vea [HTTP: Cambio a Ninguno de algunos valores predeterminados de cookie de SameSite](../../../../docs/core/compatibility/2.2-3.0.md#http-some-cookie-samesite-defaults-changed-to-none). En ASP.NET Core 3.0, la mayoría de los valores predeterminados se han cambiado de <xref:Microsoft.AspNetCore.Http.SameSiteMode.Lax?displayProperty=nameWithType> a <xref:Microsoft.AspNetCore.Http.SameSiteMode.None?displayProperty=nameWithType>, aunque se sigue usando la norma anterior.

#### <a name="reason-for-change"></a>Motivo del cambio

Cambios en el explorador y la especificación, como se ha explicado en el texto anterior.

#### <a name="recommended-action"></a>Acción recomendada

Las aplicaciones que interactúan con sitios remotos, por ejemplo mediante inicio de sesión de terceros, necesitan:

* Probar esos escenarios en varios exploradores.
* Aplicar la mitigación de detección de exploradores de la directiva de cookies tratada en [Compatibilidad con exploradores anteriores](#support-older-browsers).

Para obtener instrucciones para las pruebas y la detección de exploradores, vea la sección siguiente.

##### <a name="determine-if-youre-affected"></a>Procedimiento para determinar la afectación

Pruebe la aplicación web con una versión cliente que pueda participar en el nuevo comportamiento. Chrome, Firefox y Microsoft Edge Chromium tienen nuevas marcas de características de participación que se pueden usar para las pruebas. Compruebe que la aplicación es compatible con versiones cliente anteriores después de haber aplicado las revisiones, especialmente en el caso de Safari. Para obtener más información, vea [Compatibilidad con exploradores anteriores](#support-older-browsers).

##### <a name="chrome"></a>Chrome

Chrome 78 y versiones posteriores generan resultados de prueba engañosos. Esas versiones tienen aplicada una mitigación temporal y permiten las cookies con menos de dos minutos de antigüedad. Con las marcas de prueba adecuadas habilitadas, Chrome 76 y 77 generan resultados más precisos. Para probar el nuevo comportamiento, cambie `chrome://flags/#same-site-by-default-cookies` a habilitado. Se ha notificado que en Chrome 75 y versiones anteriores se produce un error con el nuevo valor `None`. Para obtener más información, vea [Compatibilidad con exploradores anteriores](#support-older-browsers).

Google no tiene disponibles versiones anteriores de Chrome. Sin embargo, puede descargar versiones anteriores de Chromium, lo que basta para las pruebas. Siga las instrucciones de [Descargar Chromium](https://www.chromium.org/getting-involved/download-chromium).

* [Chromium 76 Win64](https://commondatastorage.googleapis.com/chromium-browser-snapshots/index.html?prefix=Win_x64/664998/)
* [Chromium 74 Win64](https://commondatastorage.googleapis.com/chromium-browser-snapshots/index.html?prefix=Win_x64/638880/)

##### <a name="safari"></a>Safari

Safari 12 ha implementado estrictamente el proyecto anterior, con lo que se produce un error si se detecta el nuevo valor `None` en las cookies. Esto se debe evitar con el código de detección de exploradores mostrado en [Compatibilidad con exploradores anteriores](#support-older-browsers). Asegúrese de probar Safari 12 y 13, así como los inicios de sesión de estilo sistema operativo basados en WebKit mediante la Biblioteca de autenticación de Microsoft (MSAL), la Biblioteca de autenticación de Active Directory (ADAL) o cualquier biblioteca que esté usando. El problema depende de la versión del sistema operativo subyacente. Se sabe que OSX Mojave 10.14 e iOS 12 tienen problemas de compatibilidad con el nuevo comportamiento. La actualización a OSX Catalina 10.15 o iOS 13 corrige el problema. Safari no tiene actualmente una marca de participación para probar el comportamiento de la nueva especificación.

##### <a name="firefox"></a>Firefox

La compatibilidad de Firefox con la nueva norma se puede probar en la versión 68 y posteriores mediante la participación en la página `about:config` con la marca de características `network.cookie.sameSite.laxByDefault`. No se han comunicado problemas de compatibilidad en versiones anteriores de Firefox.

##### <a name="microsoft-edge"></a>Microsoft Edge

Aunque Microsoft Edge admite la antigua norma `SameSite`, a partir de la versión 44 no tiene ningún problema de compatibilidad con la nueva.

##### <a name="microsoft-edge-chromium"></a>Microsoft Edge Chromium

La marca de características es `edge://flags/#same-site-by-default-cookies`. No se ha observado ningún problema de compatibilidad al realizar pruebas con Microsoft Edge Chromium 78.

##### <a name="electron"></a>Electron

Las versiones de Electron incluyen versiones anteriores de Chromium. Por ejemplo, la versión de Electron usada por Microsoft Teams es Chromium 66, que exhibe el comportamiento anterior. Realice sus propias pruebas de compatibilidad con la versión de Electron que use el producto. Para obtener más información, vea [Compatibilidad con exploradores anteriores](#support-older-browsers).

##### <a name="support-older-browsers"></a>Compatibilidad con exploradores anteriores

La norma `SameSite` de 2016 obligaba a tratar los valores desconocidos como valores `SameSite=Strict`. Por tanto, los exploradores anteriores que admiten la norma original se pueden interrumpir al detectar una propiedad `SameSite` con un valor de `None`. Las aplicaciones web deben implementar la detección de exploradores si pretenden admitir estos exploradores antiguos. ASP.NET Core no implementa la detección de exploradores automáticamente porque los valores de encabezado de solicitud `User-Agent` son muy inestables y cambian semanalmente. En su lugar, un punto de extensión de la directiva de cookies permite agregar lógica específica de `User-Agent`.

En *Startup.cs*, agregue el siguiente código:

```csharp
private void CheckSameSite(HttpContext httpContext, CookieOptions options)
{
    if (options.SameSite == SameSiteMode.None)
    {
        var userAgent = httpContext.Request.Headers["User-Agent"].ToString();
        // TODO: Use your User Agent library of choice here.
        if (/* UserAgent doesn't support new behavior */)
        {
            options.SameSite = SameSiteMode.Unspecified;
        }
    }
}

public void ConfigureServices(IServiceCollection services)
{
    services.Configure<CookiePolicyOptions>(options =>
    {
        options.MinimumSameSitePolicy = SameSiteMode.Unspecified;
        options.OnAppendCookie = cookieContext =>
            CheckSameSite(cookieContext.Context, cookieContext.CookieOptions);
        options.OnDeleteCookie = cookieContext =>
            CheckSameSite(cookieContext.Context, cookieContext.CookieOptions);
    });
}

public void Configure(IApplicationBuilder app)
{
    // Before UseAuthentication or anything else that writes cookies.
    app.UseCookiePolicy();

    app.UseAuthentication();
    // code omitted for brevity
}
```

##### <a name="opt-out-switches"></a>Modificadores de no participación

El modificador de compatibilidad `Microsoft.AspNetCore.SuppressSameSiteNone` permite no participar temporalmente en el nuevo comportamiento de cookies de ASP.NET Core. Agregue el siguiente JSON a un archivo *runtimeconfig.template.json* del proyecto:

```json
{
  "configProperties": {
    "Microsoft.AspNetCore.SuppressSameSiteNone": "true"
  }
}
```

##### <a name="other-versions"></a>Otras versiones

Próximamente habrá revisiones de `SameSite` relacionadas para:

* ASP.NET Core 2.1, 2.2 y 3.0
* `Microsoft.Owin` 4.1
* `System.Web` (para .NET Framework 4.7.2 y posterior)

#### <a name="category"></a>Categoría

ASP.NET

#### <a name="affected-apis"></a>API afectadas

- <xref:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy%2A?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.CookieBuilder.SameSite%2A?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.CookieOptions.SameSite%2A?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.SameSiteMode?displayProperty=fullName>
- <xref:Microsoft.Net.Http.Headers.SameSiteMode?displayProperty=fullName>
- <xref:Microsoft.Net.Http.Headers.SetCookieHeaderValue.SameSite%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy`
- `Overload:Microsoft.AspNetCore.Http.CookieBuilder.SameSite`
- `Overload:Microsoft.AspNetCore.Http.CookieOptions.SameSite`
- `T:Microsoft.AspNetCore.Http.SameSiteMode`
- `T:Microsoft.Net.Http.Headers.SameSiteMode`
- `Overload:Microsoft.Net.Http.Headers.SetCookieHeaderValue.SameSite`

-->
