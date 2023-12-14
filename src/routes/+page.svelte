<script lang="ts">
    const reviews = [
        {
            title: "A Masterful Eye for Photography",
            message: "Working with Oscar for our family portraits was a delight. Their ability to capture moments with such authenticity is remarkable. We adore the photos now gracing our walls. Highly recommended!",
            name: "Emma Thompson",
            occupation: "Wedding Planner",
            avatarUrl: "/emma.png",
        },
        {
            title: "Transformative Photography",
            message: "Thankful for Oscar's expertise in capturing my portfolio. Their talent behind the lens is unmatched, opening doors for my modeling career. A true professional!",
            name: "Alex Ramirez",
            occupation: "Travel Blogger",
            avatarUrl: "/alex.png",
        },
        {
            title: "Unparalleled Excellence",
            message: "Thrilled with the moments Oscar captured. Their creative vision shines, and the final product exceeded expectations. They've immortalized cherished memories.",
            name: "Sarah Johnson",
            occupation: "CEO of a Tech Startup",
            avatarUrl: "/sarah.png",
        },
        {
            title: "A Photographer's Mastery",
            message: "Hiring Oscar for our event was a fantastic choice. Their professionalism was top-notch, seamlessly capturing the essence of our gathering. The photos are stunning!",
            name: "David Lee",
            occupation: "Business Owner",
            avatarUrl: "/david.png",
        },
    ];

    let activeGalleryTab: "nature" | "urban" | "sunset" | "cars" | "sky";
    $: activeGalleryTab = "nature";

    $: galleryPage = 0;
</script>

<div class="flex flex-col pb-32">
    <div class="flex flex-row justify-between items-center py-12 px-32">
        <div class="flex flex-row w-full">
            <a class="nav-link" href="#testimonials">Testimonials</a>
            <a class="nav-link" href="#gallery">Gallery</a>
            <a class="nav-link" href="#contact">Contact</a>
        </div>
        <div class="flex flex-col w-full items-center">
            <p class="text-2xl font-black">Oscar Falemara</p>
            <p>A Modern Photographer</p>
        </div>
        <div class="flex flex-row justify-end w-full">
            <a href="https://twitter.com/oscarfalll">
                <img
                    src="/socials/x.svg"
                    alt="x"
                />
            </a>
            <a
                class="ml-2"
                href="https://oscarfal.vercel.app"
            >
                <img
                    src="/socials/instagram.svg"
                    alt="instagram"
                />
            </a>
            <a
                class="ml-2"
                href="https://github.com/thereal-atom"
            >
                <img
                    src="/socials/facebook.svg"
                    alt="facebook"
                />
            </a>
        </div>
    </div>
    <div class="flex flex-col mt-40 px-32">
        <div class="flex flex-row justify-between w-full">
            <img
                class="w-[450px] h-[450px] rounded-md object-cover object-top"
                src="/photos/1.jpg"
                alt="1"
            />
            <div class="flex flex-col justify-between">
                <div class="flex flex-row justify-between">
                    <img
                        class="w-[200px] h-[200px] rounded-md object-cover"
                        src="/photos/2.jpg"
                        alt="2"
                    />
                    <img
                        class="w-[200px] h-[200px] rounded-md object-cover object-top"
                        src="/photos/4.jpg"
                        alt="4"
                    />
                </div>
                <img
                    class="w-[450px] h-[200px] rounded-md"
                    src="/photos/3.jpg"
                    alt="3"
                />
            </div>
            <img
                class="h-[450px] w-[200px] rounded-md"
                src="/photos/5.jpg"
                alt="5"
            />
            <div class="flex flex-col justify-between">
                <img
                    class="w-[200px] h-[200px] rounded-md object-cover"
                    src="/photos/2.jpg"
                    alt="2"
                />
                <img
                    class="w-[200px] h-[200px] rounded-md object-cover object-top"
                    src="/photos/4.jpg"
                    alt="4"
                />
            </div>
            <img
                class="h-[450px] w-[200px] rounded-md"
                src="/photos/6.jpg"
                alt="6"
            />
        </div>
    </div>
    <div class="flex flex-col items-center mt-48 px-20">
        <h2
            class="text-xl font-bold"
            id="testimonials"
        >
            Need proof that I'm good? Read people's opinions about my photography (spoiler: they like it).
        </h2>
        <div class="flex flex-row justify-between mt-48">
            {#each reviews as review}
                <div class="flex flex-col w-full rounded-md p-8 bg-[#152236] mx-8">
                    <h3 class="text-lg font-bold">{review.title}</h3>
                    <p class="text-sm mt-2 h-full">{review.message}</p>
                    <div class="flex flex-row mt-4">
                        <img
                            class="rounded-md w-12 h-12"
                            src={review.avatarUrl}
                            alt="avatar"
                        />
                        <div class="flex flex-col ml-4">
                            <p class="font-bold">{review.name}</p>
                            <p class="text-sm">{review.occupation}</p>
                        </div>
                    </div>
                </div>
            {/each}
        </div>
    </div>
    <div class="flex flex-col items-center w-full mt-48">
        <h2
            class="text-xl font-bold"
            id="gallery"
        >
            Have a look at some of my photos!
        </h2>
        <div class="gallery-tab-bar flex flex-row justify-between items-center w-full my-28 px-36">
            <button
                class="{activeGalleryTab === "nature" ? "selected" : ""}"
                on:click={() => activeGalleryTab = "nature"}
            >
                Nature
            </button>
            <button
                class="{activeGalleryTab === "urban" ? "selected" : ""}"
                on:click={() => activeGalleryTab = "urban"}
            >
                Urban
            </button>
            <button
                class="{activeGalleryTab === "sunset" ? "selected" : ""}"
                on:click={() => activeGalleryTab = "sunset"}
            >
                Sunsets
            </button>
            <button
                class="{activeGalleryTab === "cars" ? "selected" : ""}"
                on:click={() => activeGalleryTab = "cars"}
            >
                Cars
            </button>
            <button
                class="{activeGalleryTab === "sky" ? "selected" : ""}"
                on:click={() => activeGalleryTab = "sky"}
            >
                Sky
            </button>
        </div>
        <div class="flex flex-row w-full justify-between py-24 px-36">
            {#if galleryPage === 0}
                <div class="flex flex-col">
                    <img
                        class="w-[1000px] rounded-md"
                        src="/photos/sunset-1.jpg"
                        alt="sunset-1"
                    />
                    <img
                        class="w-[1000px] mt-12 rounded-md"
                        src="/photos/sunset-2.jpg"
                        alt="sunset-2"
                    />
                </div>
                <img
                    class="w-[600px] rounded-md"
                    src="/photos/sunset-3.jpg"
                    alt="sunset-3"
                />
                <!-- <button
                    class="w-[90px] relative"
                    on:click={() => galleryPage += 1}
                >
                    <img
                        class="w-full h-full object-cover object-left opacity-5 rounded-l-md"
                        src="/photos/sunset-3.jpg"
                        alt="sunset-3"
                    />
                    <div class="absolute flex items-center justify-center top-1/2 -translate-y-1/2 left-1/2 -translate-x-1/2 bg-[#406E8E] w-16 h-16 rounded-full hover:cursor-pointer">
                        <img
                            class="w-8"
                            src="/icons/chevron-right.svg"
                            alt=">"
                        />
                    </div>
                </button> -->
            {:else if galleryPage === 1}
                <div
                    class="flex flex-row w-full justify-between"
                >
                    <button
                        class="w-[90px] relative"
                        on:click={() => galleryPage -= 1}
                    >
                        <img
                            class="w-full h-full object-cover object-left opacity-5 rounded-l-md"
                            src="/photos/sunset-3.jpg"
                            alt="sunset-3"
                        />
                        <div class="absolute flex items-center justify-center top-1/2 -translate-y-1/2 left-1/2 -translate-x-1/2 bg-[#406E8E] w-16 h-16 rounded-full hover:cursor-pointer">
                            <img
                                class="w-8"
                                src="/icons/chevron-left.svg"
                                alt="<"
                            />
                        </div>
                    </button>
                    <img
                        class="w-[500px] rounded-md"
                        src="/photos/sunset-3.jpg"
                        alt="sunset-3"
                    />
                    <img
                        class="w-[500px] rounded-md"
                        src="/photos/sunset-3.jpg"
                        alt="sunset-3"
                    />
                    <img
                        class="w-[500px] rounded-md"
                        src="/photos/sunset-3.jpg"
                        alt="sunset-3"
                    />
                </div>
            {/if}
        </div>
    </div>
    <div class="flex flex-col items-center w-full mt-48 bg-[#23395B] py-32">
        <h1 class="text-4xl font-black">Think you want to work with me?</h1>
        <p class="mt-4 w-[750px] text-center">Capturing moments that last a lifetime! If you're looking for stunning photography that tells your story, I'm here to help. Feel free to reach out to me to discuss your photography needs.</p>
        <a
            class="mt-8 px-12 py-4 text-xl font-bold rounded-md bg-[#406E8E]"
            href="mailto:oscarfal2006@gmail.com"
        >
            Send me an email
        </a>
    </div>
</div>

<style lang="postcss">
    .nav-link {
        @apply text-sm mx-4 font-bold;
    }

    .gallery-tab-bar button {
        @apply font-medium text-sm opacity-40 text-[#406E8E] hover:cursor-pointer;
    }

    .gallery-tab-bar button.selected {
        @apply font-bold text-xl opacity-100 text-[#8EA8C3];
    }
</style>