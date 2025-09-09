// Mobile nav
const toggle = document.querySelector('.nav-toggle');
const links = document.querySelector('.nav-links');
if (toggle) toggle.addEventListener('click', () => links.classList.toggle('open'));

// Lightbox for gallery
const lb = document.getElementById('lightbox');
const lbInner = document.querySelector('.lightbox-inner');
const lbClose = document.querySelector('.lightbox-close');

document.querySelectorAll('.gallery img').forEach(img => {
  img.addEventListener('click', () => {
    const full = img.dataset.full;
    const type = img.dataset.type || (full.endsWith('.mp4') ? 'video' : 'image');
    lbInner.innerHTML = type === 'video'
      ? `<video src="${full}" controls playsinline></video>`
      : `<img src="${full}" alt="Full view" />`;
    lb.classList.remove('hidden');
    lb.setAttribute('aria-hidden','false');
  });
});

if (lbClose) lbClose.addEventListener('click', closeLB);
if (lb) lb.addEventListener('click', (e) => { if (e.target === lb) closeLB(); });
function closeLB(){
  lb.classList.add('hidden');
  lb.setAttribute('aria-hidden','true');
  lbInner.innerHTML = '';
}

// Contact form => WhatsApp handoff (no server needed)
const form = document.getElementById('contactForm');
const msg = document.getElementById('formMsg');

if (form) {
  form.addEventListener('submit', (e) => {
    e.preventDefault();
    const data = new FormData(form);
    const name = data.get('name')?.trim() || 'Someone';
    const email = data.get('email')?.trim() || '';
    const text = data.get('message')?.trim() || '';

    const prefill = encodeURIComponent(
      `Hi TYACDI, my name is ${name}.
Email: ${email}
Project: ${text}`
    );
    const url = `https://wa.me/2349138242248?text=${prefill}`;

    msg.textContent = 'Opening WhatsApp…';
    window.open(url, '_blank');
  });
}

// Footer year
const y = document.getElementById('y');
if (y) y.textContent = new Date().getFullYear();