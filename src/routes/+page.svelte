<!--
  This is you page!
-->
<script>
  // Import all the news furniture components
  import ArticleHeader from '$lib/components/ArticleHeader.svelte';
  import ArticleBody from '$lib/components/ArticleBody.svelte';
  import ImageWithCaption from '$lib/components/ImageWithCaption.svelte';
  import RelatedLinks from '$lib/components/RelatedLinks.svelte';
  import InflationCalculator from '$lib/components/InflationCalculator.svelte';

  // Article metadata
  let headline = 'Restaurant Costs are Still Sky-High';
  let byline = 'Irene Adeline Milanez';
  let pubDate = '2026-02-04';

  // Related stories
  const relatedStories = [
    { headline: 'What other kinds of sites will Irene make?', href: 'https://palewi.re/docs/coding-the-news/' },
    { headline: 'How to install, configure and use Visual Studio Code, GitHub and Copilot', href: 'https://palewi.re/docs/coding-the-news/scripts/week-1/' },
  ];
</script>

<!-- This sets the page title in the browser tab -->
<svelte:head>
  <title>{headline} | NYCity News Service</title>
  <meta name="description" content="At the Craig Newmark Graduate School of Journalism at the City University of New York, change is in our DNA. That comes of being born in 2006, as the digital revolution was transforming our profession in ways none of us could have imagined." />
</svelte:head>

<!-- Your page content goes here -->
<div class="container">
  
  <!-- Article Header: Headline, byline, and publication date -->
  <ArticleHeader
    {headline}
    {byline}
    {pubDate}
  />

  <!-- Lead Image: CUNY Journalism School building -->
  <ImageWithCaption
    src="/ingredients.webp"
    alt="The Craig Newmark Graduate School of Journalism is at 219 West 40th Street in Midtown Manhattan."
    caption="Cafés and bars nationwide struggle with the high cost of ingredients."
    credit="Irene Adeline Milanez"
  />

  <!-- Article Body: The main story text with proper typography -->
  <ArticleBody>
    <p>
      At Bati Ethiopian Kitchen in Brooklyn’s Bedford-Stuyvesant neighborhood, the menu centers injera, a large, sour, spongy flatbread, served with a variety of wat, stews made from meat, vegetables, and legumes.
    </p>

    <p>
      “Ethiopian food is mostly long slow-cooked stews on the fire,” owner Hibist Legesse says. “You need a lot of onions for that.” But over the past few months, Legesse has watched onions getting pricier by the day. Though the price of onions have overall decreased from 2024 to 2025 by 27.2%, from June to November of 2025, prices have fluctuated month-to-month, according to the US Bureau of Labor and Statistics Producer Price Index Report.
    </p>

    <p>
      It’s not just onions. Nearly every ingredient has gotten more expensive. The average price consumers pay for food purchases was 3.1% higher in 2025 from the previous year, according to the USDA’s Food Price Outlook.
    </p>
    <InflationCalculator />
    <p>
      Small cafés, bars and restaurants like Bati are struggling to maintain their margins as ingredient costs climb because of tariffs imposed by the Trump administration, rising inflation, and many other factors.
    </p>

    <p>
    “As an ethnic restaurant, you can only charge so much,” Legesse says. “You don’t want to push away your customers like that. So we just keep our prices the same, and we eat the cost most of the time.”    </p>

    <p>
    According to the National Restaurant Association, wholesale food prices are 37% higher than before the pandemic. Legesse says the price of meat has increased the most. The wholesale price of beef increased by 15.1% while finfish increased by 31.6% since last year, according to the Producer Price Index Report.    </p>

    <p>
      Hema Agwu, co-owner of Brooklyn Suya, says he has seen a steady rise in protein costs. His restaurants serve suya, a grilled protein seasoned with a signature Nigerian blend of roasted peanuts and dried chiles over a bed of kale or rice topped with fresh vegetables. “Steak is super expensive. Salmon is super expensive,” he says.
    </p>

    <p>
      Before the pandemic, Bati’s Legesse says her restaurant had a 6% to 7% profit margin. Today her margins hover at 5% because of ingredient price inflation, increased staffing, and higher insurance costs.
    </p>

    <p>
      The NRA estimates to maintain that slim margin, the average restaurant would have to increase menu prices by more than 30%. Few independent business owners can risk that.
    </p>
  </ArticleBody>

  <!-- Related Stories: Links to other articles -->
  <RelatedLinks
    title="Related Stories"
    links={relatedStories}
  />

</div>

<style>
  /* Styles here only apply to this page */
  .container {
    padding: var(--spacing-lg) var(--spacing-md);
  }
</style>