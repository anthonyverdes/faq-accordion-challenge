<script>
  import {faqs} from '../lib/faq-data';
</script>

<main>
  <div class="header-bg"></div>
  <div class="faq-container">
    <h1>FAQs</h1>
    {#each faqs as faq, index}
      <details open={index === 0 ? true : false}>
        <summary>{faq.question}</summary>
        <p bind:innerHTML={faq.answer} contenteditable="false"></p>
      </details>
    {/each}
  </div>
  <div class="attribution">
    <p>
      Challenge by <a href="https://www.frontendmentor.io?ref=challenge">Frontend Mentor</a>
      <br />
      Coded by <a href="https://www.frontendmentor.io/profile/anthonyverdes">Anthony Verdes</a>
    </p>
  </div>
</main>

<style>
  main {
    background-color: var(--color-light-pink);
    min-height: 100vh;
    padding-bottom: 24px;
  }

  .header-bg {
    background-image: url("/background-pattern-mobile.svg");
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    height: 232px;
  }

  .faq-container {
    background-color: var(--color-white);
    padding: 24px;
    margin: -64px 24px 0;
    border-radius: 15px;
    box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
  }

  h1 {
    position: relative;
    color: var(--color-dark-purple);
    padding-left: 40px;
  }

  h1::before {
    content: "";
    background-image: url("/icon-star.svg");
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
    position: absolute;
    top: 50%;
    left: 0;
    width: 24px;
    height: 24px;
    transform: translateY(-50%);
  }

  details {
    padding: 24px 0;
    border-bottom: 2px solid var(--color-light-pink);
  }

  details:last-child {
    border-bottom: 0;
    padding-bottom: 0;
  }

  details summary {
    position: relative;
    color: var(--color-dark-purple);
    list-style: none;
    font-weight: var(--font-weight-bold);
    padding-right: 64px;
    cursor: pointer;
  }

  details summary::after {
    content: "";
    background-image: url("/icon-plus.svg");
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
    position: absolute;
    top: 50%;
    right: 0;
    width: 32px;
    height: 32px;
    transform: translateY(-50%);
    transition: all 0.3s ease;
  }

  details[open] summary::after {
    background-image: url("/icon-minus.svg");
  }

  details summary:hover {
    color: var(--color-bright-purple);
  }

  details summary:active {
    color: var(--color-dark-purple);
  }

  details p {
    color: var(--color-gray-purple);
    font-size: 0.875rem;
    padding-top: 24px;
  }

  .attribution {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 16px 16px 0;
  }

  .attribution p {
    text-align: center;
    font-size: 0.6875rem;
  }

  /* Desktop styles */
  @media screen and (min-width: 732px) {
    .header-bg {
      background-image: url("/background-pattern-desktop.svg");
      height: 320px;
    }

    .faq-container {
      max-width: 600px;
      margin: -150px auto 0;
      padding: 32px;
    }

    h1 {
      font-size: 4rem;
      padding-left: 64px;
    }

    h1::before {
      width: 48px;
      height: 48px;
    }

    details summary {
      font-size: 1.2rem;
    }

    details p {
      font-size: 1rem;
    }

    .attribution p br {
      display: none;
    }
  }


</style>
