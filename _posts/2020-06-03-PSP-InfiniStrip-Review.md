---
layout: post
title: PSP InfiniStrip Review - Part 1
comments: true
date:   2020-06-03_14:10:00 
categories: music
tags: ['Review']
image: /assets/InfiniStrip/Banner1.png
description: Review of PSP's InfiniStrip
header: /assets/InfiniStrip/Banner1.png
header-caption: InfiniStrip Controversy...
---

I've been working with this plugin for about 7 weeks, foiled twice by circumstances while trying to get this review out.

Wait no more. With part 1 of this review, I'll be reviewing some of the controversy surrounding it and other plugins.

_**READ ME**_
**WARNING** This posts loads 45mb of media **WARNING**
_**READ ME**_

**DISCLOSURE** - PSP kindly provided this product to me for free as an NFR for review. If you believe this has biased this article, then I encourage you to call it out in the comments.

<!--more-->

**If you have any questions or comments, please comment below! I read every comment and respond to most.** No registration is necessary to comment, so don't be shy.

# Contents
{:.no_toc}
* TOC
{:toc}

# Aliasing and Cramping

If you've followed discussions about this plugin then you're familiar with these 2 complaints.

* It aliases.

* The [filters cramp]({% post_url 2017-09-18-Mixbus-32c-The-Mixer %}#cramping).

[PSP has offered](https://www.gearslutz.com/board/showpost.php?p=14670089&postcount=253) what I feel is an a _potentially_ indefensible reason for this: the plugin is meant to be zero latency, and most users utilize higher sample rates.

* Yes, _it is difficult to design a plugin that operates similar sonically with oversampling and without_.
* Yes, using higher sample rates alleviates the problem.
    * Yes, oversampling requires _more CPU_ cycles than using a higher sample rate for that specific plugin. (It increases the CPU utilization for ALL plugins used though!)
* Yes, zero latency plugins are much nicer to work with in general.

**BUT**, many other plugin designers have managed to overcome these issues and produce fantastic products with oversampling or with tricks that reduce the need for oversampling. Along with that, filter cramping can be largely alleviated with no added latency at the cost of phase response.

I'll be discussing these points, and providing both visual and audio content to help you decide if these tradeoffs are worth it.

I've been [harsh on products before for these two side effects]({% post_url 2017-09-18-Mixbus-32c-The-Mixer %}), but there's more to it than pretty graphs.

## Modeling

I believe that technical considerations need to be known, but they do not need to interfere with experience. i.e. know how your tools work, but use them how you see fit.

I have my [DAW v DAW series]({% post_url 2019-02-24-Daw-V-Daw-Differ %}) where I talk about technical differences between products. Often readers/viewers see these and come away with the idea that I think one product is suddenly inferior and _totally unusable_ because it has a deficiency in one area compared to others.

Hogwash.

Every tool has tradeoffs and deficiencies at some level. There is no magic bullet.

It does pay off to know these deficiencies or caveats so that you can work around them or work with them to further the goals that you've set for your project. This applies to all tools that you use, including plugins

**If InfiniStsrip claimed to be a circuit model or emulation of a specific hardware product, then aliasing and filter cramping would be not only false advertising, but a sizeable detraction from the total review "score".**

InfiniStrip does not claim to emulate or model any product. It's an original creation. Within that context the question becomes, "How audible is the aliasing and cramping"?

## Aliasing Part 1

{::nomarkdown}
    <video autoplay loop muted class="gifvid">
        <source src="/assets/InfiniStrip/Aliasing.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
    <div class="video-caption">Aliasing... Minor (Video)</div>
{:/nomarkdown}

I won't cover what aliasing is, since [there are](https://www.soundonsound.com/sound-advice/q-what-aliasing-and-what-causes-it) many [excellent articles](https://www.tonmeister.ca/wordpress/2018/03/18/typical-errors-in-digital-audio-part-6-aliasing/) on the [internet about](https://cecm.indiana.edu/etext/digital_audio/chapter5_nyquist.shtml) what [aliasing is](https://sites.math.washington.edu/~conroy/sequenceNoise/aliasingExamples.htm).

---

Meh. I lied. Let's cover it... backwards.

The result of aliasing is that any signal generated by the processor (plugin) that exceeds 1/2 the sample rate will be reflected back into the audible spectrum. "Mirrored" so to say. This content is _inharmonic_. The reflected content is no longer a multiple of the signal that it was related to before being reflected.

Inharmonic content is "not musical", and aliasing is one of the major reasons that digital processing gained a bad rap early on. (Along with other factors of course!).

Aliasing, in the context of this plugin, presents itself when the signal is distorted. Distortion creates harmonics ((2^n * f) of the original signal's frequency). So a 100hz sine will be turned into some harmonics of 200hz, 400hz, 800hz, 1600hz, 3200hz, 6400hz, 12800hz, 25,600hz etc...plus the original signal.

The proportion (or even existence) of each specific harmonic is not 1:1 with the original signal. Generally they decay in amplitude.

We can imagine our sampling system in terms of a box. It can represent all signals from 0 to (samplerate / 2). Let's assume a sample rate of 44,100hz. Our sampling system can now theoretically represent every sine wave between 0 and 22,050hz.

Oh no! Our distorted 100hz signal has a component of 25,600hz. That exceeds our theoretical limit. What happens now is that the the 25,600hz signal is represented as 18500hz. Our excessive signal will be represented as 18,500hz... gross!

Most distortion causes harmonics that decay in amplitude for each iteration. By time we get to 25,600, the level is fairly low. When it's reflected the amplitude is unchanged.

Hopefully the animation above shows this relationship between the harmonics, mirroring and resulting amplitude.

Depending on the distortion these aliased components may be nearly inaudible or masked by musical content.

## Aliasing Part 2

{::nomarkdown}
    <video autoplay loop muted class="gifvid">
        <source src="/assets/InfiniStrip/AliasingHigher.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
    <div class="video-caption">Aliasing... Major (Video)</div>
{:/nomarkdown}

If you were to walk away at part 1 then you would believe that aliasing isn't a big deal. The aliasing is such a low level, and it's up near the inaudible (for your average adult) frequency range.

Unfortunately, music is made up of more than a single 100hz sine. Let's try again, but with something around 10,000hz. Still in the easily audible range.

If we assume the same type of distortion then something far more destructive occurs. The aliasing extends _below_ our original signal, and retains an audible amplitude above _and_ below. In some circumstances the aliasing may even directly overlap with our original signal (but with a different envelope!!)!

Ick. Nasty.

Now we have a significant amount of inharmonic content around our original signal.

### InfiniStrip Aliasing

{::nomarkdown}
    <video autoplay loop muted class="gifvid">
        <source src="/assets/InfiniStrip/Aliasing2.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
    <div class="video-caption">Aliasing Comparison</div>
{:/nomarkdown}


Infinistrip doesn't alias _that much_, but that's not to say that there isn't some inharmonic fun bits happening.

I went through and ran a -*dBFS 997hz (the colloquial frequency of alias hunting) sine wave through InfiniStrip then checked a simple FFT plot at 48,000hz, 96,000hz, 192,000hz and 384,000hz sampling rates. That would correspond to 1x, 2x, 4x and 8x oversampling (but without the oversampling filter).

The InfiniStrip settings are extreme. I don't think anyone would run the 80s pre-amp at such high input levels with drive set to max. That's beyond crazy.

However, the most obnoxious aliasing artifact in this result is already slightly below -90dBFS. The presents of a few dozen other inharmonicities makes the overall sound more unpleasant than the amplitude of a single component would indicate. The aliasing at 48,000hz sample rate is _audible_.

Things change at 96,000hz sample rate. The aliasing becomes very subtle compared to the other higher sample rates.

Writing about it is useless though. We need to hear it. Here's audio samples with the above pictured settings in all of the pre-amp modes at various sampling rates. (Snippet from [Cory Wong by Vulfpeck](https://www.youtube.com/watch?v=AWBUnr0F3Zo)).

Here's the best way to listen:

* Click and drag on the waveform to set the cursor to the start.
* Click "Set Start"
* Click and drag on the waveform to set the cursor to the end.
* Click "Set End"
* Click the "Loop" button
* In the "s-ms-%-loop" text box, enter "loop"
* Click the play button on Cory48
* Click "Start Auto-Cycle"

The playback will loop and switch to the next version of the audio file automatically.

All files are normalized to the same perceptive loudness to reduce potential bias.

Now you tell me (in the comments or e-mail audiolabs at gmail) how impactful the aliasing is to you?

#### 60s

  <script type="text/javascript" src="/admc/comparator.js?v={{ site.time | date:'%s' }}"> </script>
  <link rel="stylesheet" type="text/css" href="/admc/admc.css">

<admc path="/assets/InfiniStrip/Audio/" title="InfiniStrip Aliasing">
	<file name="Cory60s-48khz.wav" />
	<file name="Cory60s-96khz.wav" />
	<file name="Cory60s-192khz.wav" />
	<file name="Cory60s-384khz.wav" />
</admc>

#### 70s

<admc path="/assets/InfiniStrip/Audio/" title="InfiniStrip Aliasing">
	<file name="Cory70s-48khz.wav" />
	<file name="Cory70s-96khz.wav" />
	<file name="Cory70s-192khz.wav" />
	<file name="Cory70s-384khz.wav" />
</admc>

#### 80s

<admc path="/assets/InfiniStrip/Audio/" title="InfiniStrip Aliasing">
	<file name="Cory80s-48khz.wav" />
	<file name="Cory80s-96khz.wav" />
	<file name="Cory80s-192khz.wav" />
	<file name="Cory80s-384khz.wav" />
</admc>

#### 90s

<admc path="/assets/InfiniStrip/Audio/" title="InfiniStrip Aliasing">
	<file name="Cory90s-48khz.wav" />
	<file name="Cory90s-96khz.wav" />
	<file name="Cory90s-192khz.wav" />
	<file name="Cory90s-384khz.wav" />
</admc>

### Aliasing Part 3

There's an important consideration that I've intentionally overlooked thusfar: serial non-linear processes.

Aliasing creates inharmonicities that _themselves_ can turn into more aliasing if you put another aliased processor after it. The number of inharmonicities is increased exponentially, but the amplitude of them is inversely proportional.

The secondary concern is processes like compressor and limiters which will naturally lower source material (as it's higher level than the aliasing). If you increase the gain to makeup for the compressive action, then you are increasing the inharmonicities.

I've not provided any demonstrations of this effect, but it is _highly_ dependent on the processing chain. I could easily create seemingly extreme examples that make the aliasing seem minimal, or craft an example that makes it seem unforgivably terrible. You have to try with your own material and own workflows to see if this matters to you.

## Cramping

{::nomarkdown}
    <video autoplay loop muted class="gifvid">
        <source src="/assets/InfiniStrip/Cramping.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
    <div class="video-caption">Cramping (Video)</div>
{:/nomarkdown}

Filter cramping is a bit of a complex topic, but it's easy enough to witness and to explain. Cramping is when the filter's bandwidth becomes assymetrical as it reaches the nyquist limit.

Watch the Image above for a demonstration of what this looks like.

It is possible to design a filter that is "decramped", so that the frequency response matches what you'd expect if the nyquist limit was a wall that the filter just slides behind, rather than is squished by it.

Zero-latency decramped filters aren't free. The _phase_ response of the filter is affected, and will not match that of a similar analog filter. The phase response is an audible side-effect of filters and can't be tossed aside as a consideration.

So now you have a choice between analog-like frequency response, analog-like phase response _or_ you can get _both_ by oversampling. Increase the nyquist limit and you can put the 'cramping area' well above the audible limits.

Oversampling itself imparts a sonic signature, and there's a variety of implementations with their own tradeoffs. The oversampling process also changes how processors like compressors react to the signal, thereby changing the sonic signature of the whole processor (as well as adding annoying latency).

If oversampling provides a benefit then we have a fourth option: working at a higher sample rate. Assuming that all of your other plugins work properly at higher sample rates, you have the processing power, and your hardware supports it properly then this is an ideal solution with no downsides :)

Let's ask the question though: if the only consideration is sonics, then how audible is cramping?

### InfiniStrip Cramping

{::nomarkdown}
    <video autoplay loop muted class="gifvid">
        <source src="/assets/InfiniStrip/InfiniCramp.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
    <div class="video-caption">InfiniStrip Cramping (Video)</div>
{:/nomarkdown}

The video above demonstrates the cramping present in InfiniStrip itself. With a 15khz filter there is a visual "cramping", and if we jump up to 96khz the cramping disappears.

This looks like a major issue.

As discussed before the filter can be de-cramped at the 48khz sample rate (with the tradeoff of the phase response also changing). If the designer wants the most audible "analog" feel then cramped filters would offer the ideal solution... **IF** the frequency response issue (cramping) was less audible than the phase response changes.

Let's explore this.

First I'll present another clip from Vulfpeck ([Conscious Club](https://www.youtube.com/watch?v=LqBOzFqpZzM)).

I've applied a not-cramped linear phase cut to the signal. InfiniStrip was then used to compensate for this at both 48khz and 96khz (and then downsampled to 48khz).

#### Cramping Example 1

{::nomarkdown}
    <video autoplay loop muted class="gifvid">
        <source src="/assets/InfiniStrip/Compensated.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
    <div class="video-caption">Compensated Filter Chain (Video)</div>
{:/nomarkdown}

This isn't a "definitive" test by any means, and there are some very minor artifacts caused by the compensatory filter (especially since I wrote it).

However, this simple presentation should give you an idea if the filter cramping matters to you in the context of a full mix.

<admc path="/assets/InfiniStrip/Audio/" title="Cramping">
	<file name="Club-48khz.wav" />
	<file name="Club-96khz.wav" />
</admc>

This mix doesn't have _a lot_ of high end, and I feel it'd be disingenuous to stop here, so let's try something more extreme.

#### Cramping Example 2

{::nomarkdown}
    <video autoplay loop muted class="gifvid">
        <source src="/assets/InfiniStrip/LP.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
    <div class="video-caption">Low Pass filter at various sample rates (Video)</div>
{:/nomarkdown}

Next on the list is a simple high pass filter on the mix. I took a drum track I had lying around and applied a **12.3khz** low pass filter from the "Pro Filters" in IfiniStrip.

This setup is sufficient to demonstrate the filter cramping, and a drummer bashing on cymbals _should_ be a sufficiently musical representation of "lots of high end". I also boosted the cymbals a bit to make the demonstration more audible.

(I know it doesn't "sound good", I'm intentionally trying to create an extreme example _to the benefit_ of filter cramping being potentially problematic)

<admc path="/assets/InfiniStrip/Audio/" title="Cramping">
	<file name="Drums-48khz.wav" />
	<file name="Drums-96khz.wav" />
	<file name="Drums-192khz.wav" />
</admc>

# Conclusion

If I've convinced you that Aliasing and Filter Cramping don't matter then you should stop here. **TRY IT YOURSELF**.

They matter. They are the results of tradeoffs in design _and_ potentially the result of poor design.

In the context of InfiniStrip, I think there is a case to be made that the tradeoffs are not accidental. [PSP](http://www.pspaudioware.com) is a well known developer that has made _many_ products with anti-aliasing measures and de-cramped filters. The demonstration of competency along with their stellar reputation would justify further investigation into the tradeoffs.

Given that they've made no claim of emulation or model, criticism regarding "accuracy" or "faithfulness" can be cast aside.

PSP has [publicly given reason for the presence of these side effects](https://www.gearslutz.com/board/showpost.php?p=14670089&postcount=253). Whether you accept them or not is up to you. A reasonable person would use the product in a variety of circumstances and decide if these phenomenon outweigh the benefits of the product itself.

I find it difficult to accept PSP's rationale. Many developers have managed to create channel strips that use various tricks to alleviate aliasing and filter cramping. It's clearly possible to accomplish this with the same design constraints as PSP claims they've put upon their product.

The next step is to _listen_ to the product. I can say that after 7 weeks of intensive use, I'm a _big_ fan of InfiniStrip. I've used it without thought to technical considerations and I did not once think about filter cramping. I did encounter a handful of scenarios where aliasing was bothersome in a 44.1khz project with extreme InfiniStrip settings, but I know of no other low-CPU, zero-latency channel strip that would perform well in a similar scenario.

I've not listened to _ANY_ of the comparisons I posted. They were setup using various measurement software to ensure the correct parameters were used, and I kept my speakers muted to try to avoid bias. I will not have heard these examples until I publish the article. It's possible that some bias slipped in, but I hope I've provided a wide range of examples and information about the examples for the listener to judge.

I do wish that PSP would add at least a 2x oversampling option for scenarios where extreme saturation is used, but those scenarios are relatively rare and I can simply use [my favorite saturation plugin anyway](https://klanghelm.com/contents/products/SDRR/SDRR.php). It'd be a hit to convenience, but we all make those choices everytime we load up 5+ plugins on a channel anyway :)

In short: Aliasing and Filter Cramping are real side effects of certain processes. They can be design tradeoffs, or incompetency. Sometimes they're audible, and sometimes they're not.

Accurate information interpreted correctly and applied to the right scenario is powerful. I hope that I've provided information that you can use to make better decisions about your purchase, or distaste of, InfiniStrip.


# Meta

If you feel this article was unfair in some way, please let me know!

This post took 37 hours to research, write, program, test and edit. If you appreciate the information presented then <a href="/DonateNow/">please consider joining patreon or paying us for the time spent bringing you quality content!</a>

<a href="https://www.patreon.com/bePatron?u=7465992"> <img class="patreon-button" src="/assets/Patreon.png" alt="Be a Patreon!"></a>

<form style="text-align: center;" action="https://www.paypal.com/cgi-bin/webscr" method="post" target="_top">
<input type="hidden" name="cmd" value="_s-xclick">
<input type="hidden" name="hosted_button_id" value="BR247JAZBTUJJ">
<input type="image" src="https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif" border="0" name="submit" alt="PayPal - The safer, easier way to pay online!">
<img alt="" border="0" src="https://www.paypalobjects.com/en_US/i/scr/pixel.gif" width="1" height="1">
</form>

**If you have any questions or comments, please comment below! I read every comment and respond to most.** No registration is necessary to comment, so don't be shy.
