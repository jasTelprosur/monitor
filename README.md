# Monitor Stack - SiteraPlus

Stack de monitoreo y observabilidad para la plataforma SiteraPlus.

## Componentes

- **Prometheus**: Sistema de monitoreo y series temporales
- **Grafana**: Visualización de métricas y dashboards
- **Alertmanager**: Gestión de alertas
- **Renderer**: Renderizado de imágenes de dashboards

## Estructura

```
monitor/
├── grafana/
│   └── provisioning/
│       ├── datasources/      # Configuración de fuentes de datos
│       └── dashboards/        # Dashboards preconfigurrados
├── prometheus/
│   ├── prometheus.yml         # Configuración de Prometheus
│   └── rules/                 # Reglas de alertas
├── alertmanager/
│   └── alertmanager.yml       # Configuración de Alertmanager
└── .env.example               # Variables de entorno de ejemplo
```

## Infraestructura

La infraestructura (docker-compose.yml) se encuentra en el repositorio principal:
- **Ubicación**: `docker/monitor/docker-compose.yml`
- **Datos persistentes**: `docker/data/{grafana,prometheus}`

## Configuración

1. Copiar `.env.example` a `.env` en el directorio raíz del proyecto
2. Ajustar variables de entorno según sea necesario
3. Iniciar con: `docker compose -f docker/monitor/docker-compose.yml up -d`

## Dashboards disponibles

- **Node Exporter**: Métricas del sistema operativo
- **cAdvisor**: Métricas de contenedores Docker  
- **HAProxy**: Métricas del balanceador de carga
- **Asterisk**: Métricas del servidor de telefonía
- **Mosquitto**: Métricas del broker MQTT
- **Application**: Métricas de la aplicación Laravel

## Acceso

- **Grafana**: http://localhost:3000 (usuario/contraseña configurables via .env)
- **Prometheus**: http://localhost:9090
- **Alertmanager**: http://localhost:9093

## Notas

Este repositorio contiene solo las configuraciones y definiciones.
La infraestructura Docker se gestiona desde el repositorio principal.
