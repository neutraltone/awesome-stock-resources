# frozen_string_literal: true

require 'json'

REPORT_FILE = 'ab-results-README.md-markdown-table.json'

unless File.exist?(REPORT_FILE)
  warn("awesome_bot report #{REPORT_FILE} not found. Did the workflow run the link checker?")
  return
end

results = JSON.parse(File.read(REPORT_FILE))

has_issues = results['error'] == true
has_issues ||= Array(results['errors']).any? if results.key?('errors')
has_issues ||= results['status'] == 'fail' if results.key?('status')

if has_issues
  fail(results['title'] || 'awesome_bot reported link issues')
  markdown(results['message']) if results['message']
else
  markdown('✅ awesome_bot found no link issues.')
end

