FantasyBlazor ⚽🏆

FantasyBlazor es una plataforma integral para la gestión de predicciones deportivas (conocidas como "Pollas", "Prode" o "Fantasy"). Permite a los usuarios crear grupos privados, invitar amigos y competir por puntos basados en los resultados reales de torneos de fútbol internacionales y locales.

🚀 Arquitectura del Proyecto

La solución sigue los principios de Clean Architecture, separando las responsabilidades en capas para facilitar el mantenimiento, la escalabilidad y las pruebas unitarias.

🏢 Estructura de la Solución

Proyecto	Tipo	Descripción	Patrones / Librerías
FantasyBlazor.Web	Blazor Web App	Interfaz de usuario interactiva (SSR + WASM) en .NET 10.	Blazor Components, Identity
FantasyBlazor.Application	Class Library	Lógica de negocio, orquestación de servicios y casos de uso.	AutoMapper, FluentValidation
FantasyBlazor.Domain	Class Library	Núcleo del sistema: entidades, excepciones de negocio e interfaces.	POCO Entities, Repository Interfaces
FantasyBlazor.Infrastructure	Class Library	Implementación de acceso a datos y servicios externos.	Entity Framework Core, Unit of Work
FantasyBlazor.Shared	Class Library	Recursos compartidos entre el cliente (Web) y el servidor.	DTOs, Enums, Modelos comunes

🛠️ Stack Tecnológico

Framework: .NET 10.0
Frontend: Blazor (Auto Render Mode)
ORM: Entity Framework Core
Validación: FluentValidation
Mapeo: AutoMapper
Seguridad: ASP.NET Core Identity

📋 Reglas de Negocio Implementadas (La "Polla")

El sistema calcula los puntos automáticamente basándose en las siguientes métricas:
5 Puntos: Acertar al ganador o empate (1X2).
2 Puntos: Acertar goles del equipo local.
2 Puntos: Acertar goles del equipo visitante.
1 Punto: Acertar la diferencia exacta de goles.
Bonus: Los partidos de eliminatorias (segunda ronda en adelante) otorgan doble puntaje.
⚠️ Restricción de tiempo: Las predicciones solo pueden crearse o modificarse hasta 10 minutos antes del pitido inicial.

⚙️ Configuración del Desarrollador

Clonar el repositorio.
Configurar la cadena de conexión en appsettings.json dentro de FantasyBlazor.Web.
Ejecutar migraciones: dotnet ef database update --project FantasyBlazor.Infrastructure --startup-project FantasyBlazor.Web.
Iniciar la aplicación: dotnet watch run --project FantasyBlazor.Web.

