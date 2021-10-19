# Automated Scans

## Instructions
Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quidem sed vero maiores voluptas soluta expedita, numquam nesciunt dolores itaque veritatis deleniti ratione aut vitae vel, eaque tempore illo placeat molestias ducimus doloremque! Quod quibusdam eveniet reprehenderit ab illum, dignissimos, possimus ut minima porro mollitia iusto dicta ullam eum numquam dolor eaque tempora, animi velit itaque provident. Modi vitae sint libero?

Lorem ipsum dolor, sit amet consectetur adipisicing elit. Est perferendis quasi et, quae alias aliquid saepe. Quibusdam perspiciatis similique fugit eligendi corrupti eius, maxime vero quos at iusto quod animi, ratione delectus mollitia hic temporibus. Blanditiis dignissimos dolore, id iusto fugiat quasi eum quae harum aperiam ea iure minus velit impedit tenetur incidunt temporibus sequi debitis vero eius quo illum. Modi laudantium illum sed consequatur ut quae iure expedita architecto saepe possimus nihil, minus doloribus voluptatem consectetur voluptas quis iste!

1. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Fuga atque eveniet expedita minus magni optio.

2. Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quidem sed vero maiores voluptas soluta expedita, numquam nesciunt dolores itaque veritatis deleniti ratione aut vitae vel.

## False Positives
| Scan   | Issue          | Explanation |
|:------:|:------------:|-------------|
| ASLint | SVG accessibility features | Dismiss if non-text content is pure decoration, is used only for visual formatting, or is not presented to users, then it is implemented in a way that it can be ignored by assistive technology |
| ASLint | Form input element is missing a label | Labels are not required for submit inputs |
| equal-access | Table has no headers identified | If the issue flagged is for the email alerts checkboxes this can be dismissed if the table contains role=”presentation”|

