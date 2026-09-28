# Verificador de Integridad SHA-256

Aplicación web que calcula el hash SHA-256 de un archivo y verifica su integridad comparándolo con un hash de referencia o con el mismo archivo recalculado.

## Problema que resuelve
Permite comprobar si un archivo conserva su contenido original después de ser almacenado, copiado o transmitido. Si un solo byte cambia, el hash resultante es completamente distinto.

## Tecnologías
- HTML5
- CSS3
- JavaScript

## Cómo ejecutar
1. Descargar o clonar el repositorio.
2. Abrir `index.html` en cualquier navegador moderno (Chrome, Firefox, Edge).
3. No requiere servidor ni dependencias.

## Estructura
sha256-validator/
├── index.html → Interfaz + lógica + módulo criptográfico
└── README.md → Este archivo

## Uso
1. Seleccionar un archivo.
2. Opcionalmente ingresar un hash de referencia.
3. Pulsar "Calcular hash".
4. Ver el hash, comparar con la referencia y consultar en VirusTotal.
5. Usar la sección "Pruebas de integridad" para demostrar:
   - Mismo archivo → mismo hash.
   - Archivo modificado → hash diferente.

## Arquitectura
- **Interfaz**: HTML (inputs, botones, divs de resultado).
- **Lógica de aplicación**: funciones `calcular()` y `comparar()`.
- **Módulo criptográfico**: `crypto.subtle.digest('SHA-256', buffer)`.
- **Integración VirusTotal**: enlace dinámico al reporte del hash.

## Notas
- No se almacenan archivos ni hashes en ningún servidor.
- Si el hash no existe en VirusTotal, la app lo indica al usuario.