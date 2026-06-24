# Perfil GitHub — Guía de actualización

Este archivo NO va en el repositorio. Es una guía paso a paso para que
actualices tu perfil GitHub de forma consistente con la web colvek.dev.

> **Acción recomendada:** abre `https://github.com/settings/profile` en
> una pestaña y completa cada campo según esta guía.

---

## 1. Avatar (Profile picture)

**Acción:** Subir el logo Colvek como avatar.

- Tamaño recomendado: 500×500 px
- Formato: PNG con fondo transparente o negro (#000000)
- Fuente: usa el SVG `/favicon.svg` del proyecto web y expórtalo a PNG
- Alternativa: el banner actual ya tiene el logo, recorta una versión cuadrada

**Por qué:** El avatar es la primera impresión. Coherencia visual con la web.

---

## 2. Name

```
Antuan Icaza
```

**Mantener.** Ya está bien.

---

## 3. Bio (160 caracteres máximo)

Propuesta A (recomendada, en inglés):

```
Engineering studio · AI-powered products · Built in Spain.
We ship software that works under pressure, not just impresses in demos.
```

Propuesta B (en español):

```
Estudio de ingeniería de software e IA aplicada. Hecho en España.
Construimos software que sobrevive a producción, no solo a demos.
```

Propuesta C (mixta):

```
Founder @Colvek · Software engineering + Applied AI · Spain
Websites, dashboards, apps & AI systems — built to work under pressure.
```

**Acción:** Copiar la propuesta preferida al campo Bio.

---

## 4. Company

```
Colvek
```

**Mantener.**

---

## 5. Location

```
Spain
```

**Mantener.** Si quieres ser más específico:

```
Madrid, Spain
```

o

```
Barcelona, Spain
```

Según tu ubicación real.

---

## 6. Website / Blog

**Acción:** Rellenar con:

```
https://colvek.dev
```

**Por qué:** Genera un backlink bidireccional web ↔ GitHub y aparece como
botón prominente en tu perfil.

---

## 7. Twitter / X (opcional pero recomendado)

Si tienes cuenta profesional de Twitter/X:

```
@colvek_dev
```

o tu handle personal si lo usas para temas técnicos.

**Acción:** Settings → Profile → Twitter username.

**Por qué:** Aparece como link en el perfil y refuerza presencia social.

---

## 8. Email público

**Recomendación:** NO mostrar el email real `colvek.ai@gmail.com` en el
perfil público. Mantenerlo oculto para evitar scraping.

**En su lugar:** el formulario de contacto en https://colvek.dev ya está
pensado para eso.

**Si decides mostrarlo:** usa el email noreply de GitHub:

```
273597967+Colvek@users.noreply.github.com
```

**Acción:** Settings → Emails → "Keep my email addresses private" → ON.
Luego "Don't display my email" o mostrar el noreply.

---

## 9. Hireable flag

**Acción:** Activar.

```
Settings → Profile → Available for hire → ✓
```

**Por qué:** Añade un badge verde "Available for hire" en tu perfil.
Refuerza que estás abierto a clientes.

---

## 10. Email en git config

**Acción obligatoria** para no exponer tu email en commits:

```bash
git config --global user.email "273597967+Colvek@users.noreply.github.com"
git config --global user.name "Antuan Icaza"
```

Verificar:

```bash
git config --global user.email
# Output: 273597967+Colvek@users.noreply.github.com
```

**Por qué:** GitHub asocia automáticamente este email con tu cuenta.
Tus commits en cualquier repo público quedarán vinculados a tu perfil
sin exponer el email real.

---

## 11. Two-Factor Authentication (2FA)

**Acción obligatoria.**

```
Settings → Password and authentication → Two-factor authentication → Enable
```

**Recomendado:** App TOTP (1Password, Authy, Google Authenticator) o
security key (YubiKey). Evitar SMS si es posible.

**Por qué:** Una cuenta que representa un estudio profesional NO puede
estar sin 2FA. Si la comprometen, comprometen la marca.

---

## 12. SSH / GPG keys

**Acción:** Subir al menos una SSH key y una GPG key.

```
Settings → SSH and GPG keys → New SSH key / New GPG key
```

**Para firmar commits con GPG** (recomendado para verificación "Verified"):

```bash
# Generar clave GPG
gpg --full-generate-key
# Elegir: RSA and RSA, 4096 bits, sin expiración

# Listar claves
gpg --list-secret-keys --keyid-format=long

# Configurar git para firmar
git config --global user.signingkey <KEY_ID>
git config --global commit.gpgsign true
git config --global gpg.program gpg
```

Subir la clave pública a GitHub:

```bash
gpg --armor --export <KEY_ID> | pbcopy  # macOS
# Pegar en GitHub Settings → SSH and GPG keys → New GPG key
```

**Por qué:** Commits firmados aparecen como "Verified" en GitHub.
Refuerza autenticidad y previene suplantación.

---

## 13. README del perfil

**Acción:** Hacer push del archivo `README.md` incluido en este ZIP al
repo `Colvek/Colvek`.

```bash
# Clonar
git clone https://github.com/Colvek/Colvek.git
cd Colvek

# Copiar README del ZIP sobre el existente
cp /path/to/colvek_github_fixed/README.md ./README.md

# Verificar cambios
git diff README.md

# Commit + push
git add README.md
git commit -m "feat: world-class README with embedded design system"
git push origin main
```

---

## 14. Configuración del repositorio

**Settings → General:**

| Campo                  | Valor sugerido                                |
|------------------------|-----------------------------------------------|
| Description            | `Colvek — Engineering meets obsession · Built in Spain` |
| Website                | `https://colvek.dev`                          |
| Topics                 | `portfolio`, `personal-website`, `software-engineering`, `ai-agents`, `react`, `typescript`, `spain` |
| Default branch         | `main`                                        |
| Allow squash merging   | ✓ (recomendado para mantener historial limpio) |
| Allow merge commits    | ✗                                             |
| Allow rebase merging   | ✗                                             |
| Automatically delete head branches | ✓                                  |
| Allow auto-merge       | ✗                                             |
| Wiki                   | ✗ (desactivar si no se usa)                   |
| Projects               | ✗ (desactivar si no se usa)                   |
| Discussions            | ✓ (activar para Q&A público)                  |
| Sponsorships           | ✓ (si quieres activar sponsors)               |

**Settings → Pages:**

Si quieres hospedar el contenido en GitHub Pages:

- Source: GitHub Actions
- El workflow `.github/workflows/deploy-pages.yml` está incluido en el ZIP

---

## 15. Security advisories

**Settings → Security → Code security:**

- ✅ Private vulnerability reporting
- ✅ Dependabot security updates
- ✅ Dependabot version updates (configurar `dependabot.yml` si quieres)
- ✅ Code scanning (CodeQL) — solo si añades código fuente real

---

## 16. Social previews

**Settings → Social preview:**

Subir una imagen 1280×640 px para que cuando alguien comparta tu perfil
en Twitter/LinkedIn se vea una tarjeta bonita. Recomendado: usar el
`og-image.jpg` del proyecto web colvek.dev.

---

## Checklist final

- [ ] Avatar actualizado al logo Colvek
- [ ] Bio actualizada con propuesta A/B/C
- [ ] Website = https://colvek.dev
- [ ] Twitter conectado (si aplica)
- [ ] Email oculto o usando noreply
- [ ] Hireable = ON
- [ ] git config user.email = noreply de GitHub
- [ ] 2FA activado
- [ ] SSH key subida
- [ ] GPG key subida y commit signing activado
- [ ] README.md world-class pusheado
- [ ] Description, Website y Topics configurados en el repo
- [ ] Discussions activado
- [ ] Wiki / Projects desactivados si no se usan
- [ ] Social preview subida
- [ ] Vulnerability reporting privado activado
- [ ] Dependabot activado

Una vez completado, tu perfil GitHub pasará de 32/100 a ~95/100.
