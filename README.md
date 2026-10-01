<!--
This file provides context/instruction for your repository! They are written in Markdown (.md), for simple formatting:
https://www.markdownguide.org/cheat-sheet/
-->

# Project 1: *Manuscript*

Demo/template for our [first projects](https://typography-interaction-2627.github.io/project/1/).

> **Students will choose a seminal design text from [readings.design](https://readings.design), read and respond to it, and typeset their selection and reply together.**
>
> The goal of this project is to hone your basic skills in typography, focusing on expression, hierarchy, and form appropriate to a work. You will do this through exploration, trial and error, and responding to critical feedback. And then you will execute this typesetting in code, as a web page

# Manuscript: Project 1
## Concept Behind the Web Design
I drew upon the work of the group Metahaven, which felt more contemporary and consisted of more minimalist designs that use spacing and background boxes behind type to illustrate a hierarchy. A lot of their work felt very simple but intentional, which I tried to recreate through the tree in the code that comes later. It also borrows a lot from Marxist thinkers like Antonio Gramsci and Francis Fukuyama, who explain the exact magnitude of the influence of Western powers around the globe. This influenced my response, where I go into detail on the new rebranding of the US government led by Donald Trump, who recognizes the importance of brand and how it can be co-opted by more influential figures. This design studio included the former founder of Airbnb, which influenced the typeface choices you see throughout the work. Most of these fonts you would find plastered across SaaS websites, but I also wanted to include some more classic fonts that are associated with status, such as Garamond and the new, trendy condensed serif Instrument Serif. While the font scale does not change much between heading 1, heading 2, and paragraph, I wanted to balance that with larger moments that include bigger margins between sections, such as the quote and the introduction paragraph for both the article and the response. I use the em tag to create the illustration of the American flag, combining it with the white paragraph type to create a more ironic feeling and a parody of the United States branding project. This includes the use of only the American flag colors, but heightened to contrast with the duller navy background. These bright moments are not used overwhelmingly, but appear throughout the key moments in the manuscript, like figures that are mentioned and more verbose words that are used more as jargon for critical theory than design. It's because of this that I decided to go with this interaction pattern, where clicking on a vocab word transports you to its key. A hover state is included to signal to the user that it is interactable. I imagine that a lot of designers are not too familiar with many of the concepts that the essay contains, so I decided to ease that with smaller asides at the end of sections that help illustrate or explain any person or concept that seems difficult.
# The Code Structure

## Typography
The typography is assigned based on a 4px grid, meaning that every font size and leading value is a multiple of 4 to keep the typographic scale cohesive. This all originates with 1rem, which serves as the base unit that dictates all the sizes throughout the website. However, the leading does not grow with the type scale and is hardcoded through multiples of the base grid unit.

/* The whole system is based on the baseline grid I created for my sketch. That's initially why all the variables are filled. */

--base-unit: 1rem;
--type-grid: calc(var(--base-unit) * 0.25);

/* sizes */
/* To match the spacing of my old text, I wanted everything to be divisible by 4, so I took the body paragraph and created a 1.25 ratio for it. As it multiplied further, it got as close as I could to the original sizing of my code. I then just rounded each size to the nearest multiple of 4 to get them all evened out. */
--text-xs: calc(var(--type-grid) * 3);
--text-s: calc(var(--type-grid) * 4);
--text-m: calc(var(--type-grid) * 5);
--text-l: calc(var(--type-grid) * 6);
--text-2xl: calc(var(--type-grid) * 10);

/* types */

--text-article-body-paragraph: var(--text-m);
--text-header-subtext: var(--text-s);
--text-heading-title: var(--text-2xl);
--text-article-body-lead: var(--text-2xl);
--text-heading-one: var(--text-l);
--text-quoteblock-quote: var(--text-2xl);
--text-module: var(--text-l);
--text-label: var(--text-xs);
--text-source: var(--text-s);
--text-description: var(--text-xs);
--text-cite: var(--text-m);
--text-footnote:var(--text-xs);
--text-dropcap: calc(var(--text-article-body-lead) * 6);

--leading-xs: calc(var(--type-grid) * 4);
--leading-s: calc(var(--type-grid) * 6);
--leading-m: calc(var(--type-grid)* 7);
--leading-l: calc(var(--type-grid) * 8);
--leading-2xl: calc(var(--type-grid) * 11);
Spacing
--space-paragraph-bottom: calc(var(--base-unit) * 2.5);




/* branch of the tree: paragraph-bottom -> */
--space-heading-bottom: calc(var(--space-paragraph-bottom) * 4);
--space-quote-text-bottom: calc(var(--space-paragraph-bottom) * .5);
--space-subsection-bottom: calc(var(--space-paragraph-bottom) * 1.5);
--space-article-section-bottom: calc(var(--space-paragraph-bottom) * 2);
--space-heading1-bottom: calc(var(--space-paragraph-bottom) * .5);
--space-page-top: calc(var(--space-paragraph-bottom) * 2);

/* padding: these also start from paragraph-bottom */

--space-chip-padding-block: calc(var(--space-paragraph-bottom) * 0.1);
--space-module-padding: calc(var(--space-paragraph-bottom) * 0.4);


/* padding -> paragraph -> module-padding */
--space-panel-padding-block: calc(var(--space-module-padding) * .75);
--space-panel-padding-inline: calc(var(--space-module-padding) * 1.5);




/* padding: paragraph -> chip-block */
--space-chip-padding-inline: calc(var(--space-chip-padding-block) * 2);
--space-button-padding-block: calc(var(--space-chip-padding-block) * 2);

/* paragraph -> chip-block -> chip-inline */
--space-button-padding-inline: calc(var(--space-chip-padding-inline) * 2);
--radius-chip: calc(var(--space-chip-padding-inline) * 1);

/* paragraph -> chip-block -> chip-inline -> radius-chip */
--radius-dropcap: calc(var(--radius-chip) * 0.5);
--radius-button: calc(var(--radius-chip) * 1);

--radius-panel: calc(var(--space-module-padding) * 1);




/* paragraph -> space-subsection-bottom */
--space-page-inline: calc(var(--space-subsection-bottom) * 1);

/* branch of paragraph-bottom -> heading1-bottom */
--space-author-bottom: calc(var(--space-heading1-bottom) * 0.4);


/* paragraph -> space-article-section-bottom */
--space-intro-bottom: calc(var(--space-article-section-bottom)* 1);
--space-quote-top: calc(var(--space-article-section-bottom) * 2);

/* paragraph -> space-article-section-bottom -> space-quote-top */
--space-quote-bottom: calc(var(--space-quote-top) * 1);

--space-article-bottom: calc(var(--space-quote-top) * 1.5);

--space-header-bottom: calc(var(--space-quote-top) * 1);


/* paragraph-bottom -> space-module-padding */
--space-module-bottom: calc(var(--space-module-padding) * 1);
--space-label-bottom: calc(var(--space-module-padding) * 0.5);
--space-panel-top: calc(var(--space-module-padding)* 1);
--space-source-bottom: calc(var(--space-module-padding) * 1);
--space-footer-citation-bottom: calc(var(--space-paragraph-bottom)*0.5);
--space-footer-link-bottom: calc(var(--space-footer-citation-bottom) * 1);
--space-button-top: calc(var(--space-paragraph-bottom) * .5);
--space-quote-padding-inline: calc(var(--space-article-section-bottom) * 1.5);
--radius-module: calc(var(--space-module-padding) * 1.25);
--radius-panel: calc(var(--space-module-padding) * 1);

The spacing follows a similar rule, with every value being a multiple of 4. It all starts with the seed, which in this case is the paragraph-bottom padding, and it affects the value of the spacing throughout the entire tree. This branches into three categories, the first being the vertical margin, which builds on the idea of scaling up the spacing as the type increases in size. Within the vertical margin, the paragraph affects all the bigger nested modules that contain their own text hierarchies, such as a header. It also influences the more deeply nested elements, like the chip padding, the cards, and the columns. Some values were not included within this tree, like the drop cap, which is translated backwards from px values, and similarly the big spacing gap within the h2 that breaks out of the hierarchy created within the nest of the article body. The padding within the cards also does not follow this tree, which limits the relational system created.

## Columns
This was the biggest failure, which I tried to fix but was unable to. I decided to use inline-block to adjust and control the values of the two columns so they could sit next to each other. This would aid my attempt to have the asides actually sit next to the text. However, since percentages are relative to the screen width, it does break a bit when the screen takes on dimensions that are not akin to a laptop display. That being said, I still think the two-column approach aids this interaction rather than inhibiting it.

