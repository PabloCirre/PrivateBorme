# OpenBorme

**OpenBorme** es una plataforma de ingeniería de datos abierta que estructura, normaliza y publica el **Boletín Oficial del Registro Mercantil (BORME)** de España.

Nuestro objetivo es democratizar el acceso a la información empresarial mediante un pipeline reproducible, transparente y ético.

[![Estado](https://img.shields.io/badge/Estado-Activo-success)](https://openborme.es)
[![Licencia](https://img.shields.io/badge/Licencia-MIT-blue)](LICENSE)
[![Datos](https://img.shields.io/badge/Datos-ODbL-green)](http://opendatacommons.org/licenses/odbl/)

## 🌐 Entornos y Pruebas

Puedes visualizar y probar el proyecto en los siguientes entornos:

* **Producción**: [openborme.es](https://openborme.es/) (Versión estable y pública).
* **Local**: Sigue los pasos de instalación abajo para ejecutar una instancia local en `http://localhost:8000`.

## 🚀 Características

* **Ingesta Automática**: Descarga diaria de sumarios XML y PDFs de la [Agencia Estatal BOE](https://www.boe.es).
* **Extracción OCR**: Procesamiento de documentos PDF (Sección I) para extraer texto plano estructurado.
* **Normalización**: Limpieza de entidades, fechas y tipos de actos.
* **Trazabilidad**: Generación de hashes MD5 para garantizar la integridad del texto extraído frente al original.
* **Frontend Ligero**: Interfaz web PHP sobria y rápida, sin rastreadores ni publicidad.

## 📁 Estructura del Proyecto

* **`pipeline/`**: Motor de extracción y procesamiento (Python).
* **`public_html/`**: Interfaz web y API (PHP/CSS).
* **`ops/`**: Scripts de despliegue y mantenimiento.
* **`docs/`**: Documentación técnica y estratégica.
* **`data/`**: Almacenamiento local de documentos BORME (vía `pipeline`).

## 🛠️ Instalación (Local)

1. **Requisitos**: PHP 8.x, Python 3.10+.
2. **Web**: Sirve el directorio `public_html`.

    ```bash
    php -S localhost:8000 -t public_html
    ```

1. Clonar el repositorio:

    ```bash
    git clone https://github.com/PabloCirre/OpenBorme.git
    cd OpenBorme
    ```

4. Instalar dependencias de Python (Pipeline):

    ```bash
    cd pipeline
    pip install -r requirements.txt
    ```

5. Instalar dependencias de PHP (Web/Parsers):

    ```bash
    composer install
    ```

6. Configurar entorno:

    ```bash
    cp ops/env.example .env
    # Editar .env con tus rutas locales
    ```

## 🤝 Contribuciones

Las contribuciones son bienvenidas, especialmente en mejoras de parsers y detección de errores OCR. Por favor lee [CONTRIBUTING.md](CONTRIBUTING.md) antes de enviar un Pull Request.

## 📄 Licencia

* **Código**: MIT License (ver [LICENSE](LICENSE)).
* **Datos Derivados**: Open Database License (ODbL). Debes atribuir a OpenBorme y al BOE al reutilizar los datos.

## 🔒 Privacidad

Este proyecto respeta estrictamente el RGPD. El módulo de búsqueda de personas físicas está **desactivado por defecto**. No se permite el uso del código para la creación de perfiles personales masivos. Ver [docs/MANIFIESTO_TECNICO.md](docs/MANIFIESTO_TECNICO.md).

---
*Desarrollado con ❤️ por Pablo Cirre.*


---

## 📊 Módulos Analíticos, Calculadoras Mercantiles (LSC/TRLC) y Estudios Macroeconómicos 2026

Este repositorio incluye motores deterministas en Python (`calculators/spain_fiscal_engines_2026.py`, sin dependencias externas) y series primarias normalizadas en CSV/JSON (`data/spain_treasury_housing_corporate_2026.csv`, `data/spain_macro_fiscal_2026.json`) desarrollados junto al equipo de investigación de **[Diario Económico (`diarioeconomico.net`)](https://diarioeconomico.net/)**, **[Hub de Calculadoras Económicas](https://diarioeconomico.net/calculadoras/)**, **[Estudios Económicos y Dossiers INE/BdE](https://diarioeconomico.net/estudios/)** y **[Consulta Jurídica Mercantil y Societaria](https://diarioeconomico.net/consulta-abogado/)**.

### 🧮 Calculadoras Interactivas y Documentación Técnica de Referencia

| Área / Motor en Python | Herramienta Web Interactiva | Estudio / Guía Jurídica y Económica de Referencia | Fuente Oficial |
| :--- | :--- | :--- | :--- |
| **Letras del Tesoro (ACT/360 + AEAT)** | [Calculadora de Letras del Tesoro 2026](https://diarioeconomico.net/calculadoras/letras-del-tesoro/) | [Subastas Letras del Tesoro Nov-Dic 2026: Fechas y Rentabilidad](https://diarioeconomico.net/invertir-en-letras-del-tesoro-calendario-de-subastas-noviembre-diciembre-2026-y-rentabilidad-real/) · [Guía Completa para Comprar Letras en Banco de España](https://diarioeconomico.net/como-invertir-en-letras-del-tesoro-2026-guia-completa-para-comprar-en-el-banco-de-espana-rentabilidad-y-comisiones/) | Tesoro Público · BdE · Ley 35/2006 |
| **IRPF 2026 (17 CCAA) y Salario Neto** | [Calculadora de Sueldo Neto e IRPF 2026](https://diarioeconomico.net/calculadoras/sueldo-neto-irpf/) | [Calculadora IRPF 2026 y Tablas por CCAA](https://diarioeconomico.net/calculadora-irpf-2026-sueldo-neto-espana-tramos-ccaa/) · [Evolución del SMI en España y Coste Laboral](https://diarioeconomico.net/evolucion-salario-minimo-espana/) | AEAT · Seguridad Social |
| **Hipotecas, Euríbor y Amortización Anticipada** | [Simulador de Hipoteca y Amortización](https://diarioeconomico.net/calculadoras/hipoteca-amortizacion/) | [Amortizar Hipoteca: ¿Reducir Cuota o Plazo?](https://diarioeconomico.net/amortizar-hipoteca-reducir-cuota-o-plazo-simulador-ahorro/) · [Tipos de Interés BCE y Euríbor](https://diarioeconomico.net/tipos-interes-bce/) | Banco de España · BCE |
| **IPC, Alquileres (IRAV) y Poder Adquisitivo** | [Calculadora de IPC y Poder Adquisitivo](https://diarioeconomico.net/calculadoras/ipc-poder-adquisitivo/) | [Cómo Actualizar una Renta o Salario con el IPC](https://diarioeconomico.net/actualizar-renta-alquiler-salario-ipc-espana/) · [Estudio IPV Vivienda INE](https://diarioeconomico.net/precio-vivienda-espana-ipv-ine/) | INE (IPC / IRAV / IPV) |
| **Derecho de Separación y Dividendo Mínimo (Art. 348 bis LSC)** | `evaluate_art_348_bis_lsc()` | [Derechos del Socio Minoritario en una SL: Impugnación de Acuerdos y Separación (Art. 348 bis LSC)](https://diarioeconomico.net/derechos-socio-minoritario-sl-impugnar-acuerdos-reparto-dividendos/) | RDL 1/2010 (LSC) |
| **Responsabilidad Solidaria del Administrador (Art. 367 LSC)** | `evaluate_director_liability_art367()` | [Responsabilidad del Administrador de una SL por Deudas y Cierre sin Liquidar](https://diarioeconomico.net/responsabilidad-administrador-sl-deudas-cierre-sin-liquidar-como-reclamar-socios/) | Arts. 236–241 y 363–367 LSC |
| **Concurso de Acreedores y Segunda Oportunidad (TRLC)** | [Consulta Mercantil y Concursal](https://diarioeconomico.net/consulta-abogado/) | [Cuándo Solicitar Concurso de Acreedores en una Pyme y Evitar Derivación](https://diarioeconomico.net/concurso-acreedores-pymes-cuando-es-obligatorio-segunda-oportunidad-administrador/) | RDL 1/2020 (TRLC) · Ley 16/2022 |
| **Morosidad Comercial y Contratos Públicos (Ley 3/2004 y LCSP)** | `calculate_late_payment_claim()` | [Cómo Reclamar Facturas Impagadas a Clientes Morosos: Proceso Monitorio y Ley 3/2004](https://diarioeconomico.net/como-reclamar-facturas-impagadas-clientes-morosos-proceso-monitorio-intereses-ley-3-2004/) · [Dimisión en Transportes y Licitaciones ADIF (Ley 9/2017)](https://diarioeconomico.net/dimision-ministro-transportes-impacto-licitaciones-adif-obra-publica/) | Ley 3/2004 · Ley 9/2017 (LCSP) |
| **Inversores Bursátiles y Caso Soltec (CNMV / LMVSI)** | [Consulta de Litigación Financiera](https://diarioeconomico.net/consulta-abogado/) | [Cómo Reclamar Pérdidas en Acciones por Cuentas Falsas o Suspendidas en CNMV](https://diarioeconomico.net/reclamar-perdidas-acciones-empresa-auditada-suspendida-cnmv-guia-inversores/) · [Caso Soltec en la Audiencia Nacional](https://diarioeconomico.net/audiencia-nacional-investiga-soltec-200-millones-inversores-bolsa/) | Ley 6/2023 (LMVSI) · Art. 1101 CC |
| **Demografía Empresarial DIRCE, INE, Empleo y Comunicación** | `data/spain_treasury_housing_corporate_2026.csv` | [Costes Laborales ETCL INE](https://diarioeconomico.net/coste-laboral-espana-etcl-ine/) · [Demografía Empresarial DIRCE](https://diarioeconomico.net/tejido-empresarial-espana-dirce-pymes/) · [Creación de Sociedades Mercantiles INE](https://diarioeconomico.net/creacion-disolucion-sociedades-mercantiles-espana/) · [Reanudación Subsidio SEPE](https://diarioeconomico.net/como-solicitar-la-reanudacion-de-un-subsidio-por-desempleo/) · [Facturar sin ser Autónomo](https://diarioeconomico.net/como-facturar-sin-ser-autonomo-en-espana-limites-hacienda-seguridad-social/) · [Publicar Nota de Prensa](https://diarioeconomico.net/publicar-nota-de-prensa/) · [Precios de Notas de Prensa en Medios](https://diarioeconomico.net/cuanto-cuesta-publicar-nota-de-prensa-espana-donde-enviar-medios/) | INE · BORME · SEPE |
