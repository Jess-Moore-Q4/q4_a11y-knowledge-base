# Automated Scans

## Scanner Instructions
To conduct an internal scan using EssentialAccessibility's automated scanning tool:

1. Log into the [EA dashboard](https://dashboard.essentialaccessibility.com/) with your account

2. Ensure you are on the correct digital property - on the left-menu under "Digital Property", select the `Q4 Client Sites > Default` property - then click "Run Automated Scan" from the same left-menu

3. From the "Run Automated Scan" landing page, click the "Setup advanced scan" button

4. Follow the form prompts to fill out the required fields:
    - Scan tag should be `default`

    - Select "List of pages" to scan multiple pages."Crawl a website" is not reccomended as the scanner will include each individual details pages (ie press releases)

5. **Optional:** Add authentication details to scan previews by completing the following:
    1. Change the Authentication type select to `Secure web authentication`

    2. User Name Fields:
        - Your CMS User Name
        - HTML Field Selector: `#txtUserName`

    3. Passowrd Fields:
        - Your CMS Password
        - HTML Field Selector: `#txtPassword`

    4. HTML submit button selector: `#btnSubmit`

    5. HTML success element selector: `#pageClass`

6. Ensure that “Accessibility”, “WCAG 2.1 Level AA” and “Desktop” are selected (will be by default), then click “Run Scan”

7. Scan will appear in the list of scans under the "Scans" tab of the left-menu, the results will be available by clicking the "Scan results" button once complete


## False Positives
| Accessibility Testing Tool | Issue          | Explanation |
|----------------------------|----------------|-------------|
| **ASLint** | SVG accessibility features | According to the [WCAG](https://www.w3.org/WAI/WCAG21/Understanding/name-role-value#sufficient), "Text or images of text that are part of an inactive user interface component, that are pure decoration, that are not visible to anyone, or that are part of a picture that contains significant other visual content, have no contrast requirement." |
| **ASLint** | Form `<input>` element is missing a label | Labels are not required for submit inputs |
| **equal-access** | Table has no headers identified | If the issue flagged is for the email alerts checkboxes this can be dismissed if the table contains role=”presentation” |
| **equal-access** | The input element does not have an associated visible label | This issue appears even if inputs have an aria label. According to the [WCAG](https://www.w3.org/WAI/WCAG21/Understanding/name-role-value#sufficient), aria-labels are a sufficient alternative |
| **equal-access** | The WAI-ARIA role or attribute is not valid for the specified element | During manual testing, our accessibility partner, Essential Accessibility has specifically asked for the following roles to be on the following elements:<ul><li>role=”status”, search results `<h2>`</li><li>aria-required, email alert checkboxes</li></ul>Dismiss if part of stock chart SVG as the graphic cannot be reached by screenreader / keyboard. Accessible data table has been provided |
| **equal-access** | `<label>` is associated with an inappropriate element | If flagged on the grouping of email alert checkboxes, and the element with the ID that matches the for attribute exists, this can be dismissed |
| **equal-access** | Check the keyboard focus indicator is highly visible when using CSS elements for border or outline | Dismiss for svg elements of the stock chart (not reachable via keyboard, and accessible data table has been provided). <br>Dismiss if you’ve visually confirmed a focus state is visible. |
| **equal-access** | Interactive component does not have a programmatically associated name | Dismiss of part of the stock chart SVG. Graphic not reachable by keyboard / screen reader or accessible data table has been provided |
| **equal-access** | Accessible name does not match or contain the visible label text | Dismiss if the aria-label does not match because it’s being used to provide more context to an otherwise vague link (ie “Read More”) <br/><br/>Dismiss if aria-label is being used to describe a link that is an image |
| **equal-access** | An element with a "region" role does not have a label | Dismiss if using described-by attribute |


