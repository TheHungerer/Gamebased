// Scroll Reveal Animation
const reveals = document.querySelectorAll('.reveal');

const observer = new IntersectionObserver((entries) => {
  entries.forEach((entry, index) => {
    if (entry.isIntersecting) {
      setTimeout(() => {
        entry.target.classList.add('visible');
      }, index * 100);

      observer.unobserve(entry.target);
    }
  });
}, { threshold: 0.15 });

reveals.forEach((el) => observer.observe(el));